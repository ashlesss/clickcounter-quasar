<template>
  <q-layout view="hHh lpR fFf">
      <q-header reveal elevated v-bind:class="headerClass">
        <q-toolbar>
          <q-btn dense flat round icon="menu" @click="drawerOpen = !drawerOpen" />
  
          <q-toolbar-title>
            Click Counter
          </q-toolbar-title>

          <div>
            <q-btn flat round color="white" icon="dark_mode" @click="toggleDark"/>
          </div>
        </q-toolbar>
      </q-header>

    <q-drawer
        v-model="drawerOpen"
        show-if-above 

        :mini="miniState"
        @mouseover="miniState = false"
        @mouseout="miniState = true"

        :width="200"
        :breakpoint="500"
        bordered
        :class="$q.dark.isActive ? 'bg-grey-9' : 'bg-grey-3'"
      >
        <q-scroll-area class="fit" :horizontal-thumb-style="{ opacity: 0 }">
          <q-list padding>
            <q-item 
            to="/"
            clickable 
            v-ripple
            exact>
              <q-item-section avatar>
                <q-icon name="info" />
              </q-item-section>

              <q-item-section>
                How 2 use
              </q-item-section>
            </q-item>

            <q-item 
            to="/click_counter"
            exact
            clickable 
            v-ripple>
              <q-item-section avatar>
                <q-icon name="apps" />
              </q-item-section>

              <q-item-section>
                Click Counter
              </q-item-section>
            </q-item>
            

          </q-list>
        </q-scroll-area>
      </q-drawer>

    <q-page-container>
      <keep-alive>
        <router-view />
      </keep-alive>
    </q-page-container>
  </q-layout>
</template>

<script>
import { defineComponent, ref } from 'vue'
import { useQuasar } from 'quasar'

export default defineComponent({
  name: 'MainLayout',

  setup() {
    const $q = useQuasar();
  },

  data() {
    return {
      drawerOpen: ref(false),
      miniState: ref(true),
      isDarkActive: false,
    }
  },

  computed: {
    headerClass() {
      return {
        'bg-primary text-white': !this.isDarkActive,
        'bg-dark text-white': this.isDarkActive
      }
    }
  },

  methods: {
    toggleDark() {
      if (this.$q.dark.isActive == false && this.$q.dark.mode == false) {
        this.$q.dark.set(true);
        this.isDarkActive = true;
      }
      else {
        this.$q.dark.set(false);
        this.isDarkActive = false;
      }
    }
  }
})
</script>
