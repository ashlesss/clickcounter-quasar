<template>
    <div class="flex flex-center" style="height: 100px;  margin-right: 15px">
        <h5 >
            <b>Saved Number :</b>
            <p class="flex flex-center" style="color: rgb(255, 0, 0); font-weight: bold;">{{ savedNum }}</p>
        </h5>
    </div>
    <div class="flex flex-center q-mt-xs">
        <q-input
            input-class="text-center"
            input-style="font-size: 2em"
            v-model.number="model"
            type="number"
            filled
            style="max-width: 250px">  
        </q-input>
    </div>
    <div class="flex flex-center q-mt-xs">
        <q-btn 
        size="40px"
        style="width: 100%; background-color: #198754;" 
        text-color="white" 
        padding="none"
        label="+" 
        @click="add" />
    </div>
    <div class="flex flex-center q-mt-xs">
        <q-btn 
        size="25px"
        style="width: 100%; background-color: #198754;" 
        text-color="white" 
        padding="none"
        label="-"
        @click="min" />
    </div>
    <div class="row q-mt-xs">
        <q-btn 
        style="flex-grow:1; background-color: #198754; max-width: 50%" 
        text-color="white" 
        label="+100"
        @click="plus100" />
        <q-btn 
        style="flex-grow:1; background-color: #198754; max-width: 50%" 
        text-color="white" 
        label="-100"
        @click="min100" />
    </div>
    <div class="row q-mt-xs">
        <q-btn 
        style="flex-grow:1; background-color: #198754; max-width: 50%" 
        text-color="white" 
        label="-00"
        @click="min00" />
        <q-btn 
        style="flex-grow:1; background-color: #198754; max-width: 50%" 
        text-color="white" 
        label="-0"
        @click="min0" />
    </div>
    <div class="row q-mt-xs">
        <q-btn 
        style="flex-grow:1; background-color: #198754; max-width: 50%;" 
        text-color="white" 
        label="Save Number"
        @click="saveNum" />
        <q-btn 
        style="flex-grow:1; background-color: #198754; max-width: 50%;" 
        text-color="white" 
        label="To save"
        @click="toSave" />
    </div>
    <div class="row q-mt-xs">
        <q-btn 
        style="width: 100%; background-color: #198754;" 
        text-color="white" 
        label="Reset"
        @click="reset" />
    </div>
    <div class="row q-mt-xs">
        <q-btn  
        style="width: 100%; background-color: #198754;" 
        text-color="white" 
        label="Reset Saved"
        @click="resSave" />
    </div>
</template>

<script>
import { defineComponent, ref } from 'vue';

export default defineComponent({
    name: 'AllBtns',

    // setup() {
    //     return {
    //         model: ref(0)
    //     }
    // },

    data() {
        return {
            model: ref(0),
            savedNum: 0,
        }
    },

    methods: {
        add() {
            this.model++
        },

        min() {
            this.model--
        },

        plus100() {
            this.model = this.model + 100;
        },

        min100() {
            this.model = this.model - 100;
        },

        min00() {
            if (this.model > 0) {
                this.model = Math.floor(this.model / 100 ) * 100;
            }
            else {
                this.model = Math.ceil((this.model * -1) / 100) *100 * -1;
            }
        },

        min0() {
            if (this.model > 0) {
                this.model = Math.floor(this.model / 10 ) * 10;
            }
            else {
                this.model =Math.ceil((this.model * -1) / 10) * 10 * -1;
            }
        },

        saveNum() {
            this.savedNum = this.model;
        },

        toSave() {
            if (this.savedNum !== 0) {
                this.model = this.savedNum;
            }
        },

        reset() {
            this.model = 0;
        },

        resSave() {
            this.savedNum = 0;
        }
    },
    
})

</script>
