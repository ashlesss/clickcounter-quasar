<template>
  <q-page class="flex flex-center">
    <UsageIntro />
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
