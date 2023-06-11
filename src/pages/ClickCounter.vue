<template>
    <q-page class="flex flex-center flex-col">
      <div>
      <AllBtns />
      </div>
    </q-page>
  </template>
  
  <script>
  import { defineComponent, ref } from 'vue'
  import AllBtns from 'components/AllBtns.vue'
  
  export default defineComponent({
    name: 'ClickCounter',
    
    components: {
      AllBtns,
    },

    // setup() {
    //   return {
    //     model: ref(0),
    //   }
    // },

    // data() {
    //   return {
    //     model: ref(0)
    //   }
    // },

    // created() {
    //     console.log(this.model);
    // }
  })
  </script>