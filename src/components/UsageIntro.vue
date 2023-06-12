<template>
    <div class="column">
        <h2>
            Welcome to my Click counter mini application.
        </h2>
        <p class="style">Usage: </p>
        <ol>
            <li style="font-size: 1.2rem" v-for="(con, index) in cons" :key="index">
                <code 
                :style="codeStyle">
                {{ con.cmd }}
            </code> 
            -- {{ con.desc }}
            </li>
        </ol>
    </div>
</template>

<script> 
import { defineComponent } from 'vue'
import { useQuasar } from 'quasar'

export default defineComponent({
    name: 'UsageIntro',

    setup() {
        const $q = useQuasar();
    },

    data() {
        return { 
            cons: [
                {cmd: '-00', desc: 'This will zeroing last 2 digits(tens). For example: 188 ==> 100.'},
                {cmd: '-0', desc: 'This will zeroing the last 1 digit(ones). For example: 188 ==> 180.'},
                {cmd: 'ToSave', desc: 'This will set the current number to your saved number marked red on the top.'},
                {cmd: 'RESET', desc: 'This will reset the current number but will not reset the Saved number.'},
            ],
        }
    },

    computed: {
        codeStyle() {
            if (this.$q.dark.isActive == true) {
                return 'background-color: #464646; color: white; padding: 2px; border-radius: 5px';
            }
            else {
                return 'background-color: #4a80ff; color: white; padding: 2px; border-radius: 5px';
            }
        }
    }

})
</script>

<style scoped>
.column :deep() .style {
    font-size: 1.5rem
}
</style>