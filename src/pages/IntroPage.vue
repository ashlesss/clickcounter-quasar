<template>
  <q-page class="flex flex-center">
    <div class="column">
      <UsageIntro />
      <div class="flex flex-center absolute-bottom" style="font-size: 1rem;">
        This project is built by&nbsp;<a href="https://ashless.io" target="_blank">Ashless</a>&nbsp;and using&nbsp;<a href="https://quasar.dev/" target="_blank">Quasar Framework</a>
      </div>
    </div>
  </q-page>
</template>

<script>
import { defineComponent } from 'vue'
import UsageIntro from 'components/UsageIntro.vue'

export default defineComponent({
  name: 'IndexPage',

  components: {
    UsageIntro,
  },
})
</script>
