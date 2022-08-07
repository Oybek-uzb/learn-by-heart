<template>
  <q-layout view="hHh LpR fff">

    <q-header elevated className="bg-primary text-white">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer"/>

        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
          </q-avatar>
          Title
        </q-toolbar-title>

        <q-btn dense flat round icon="menu" @click="toggleRightDrawer"/>
      </q-toolbar>
    </q-header>

    <q-drawer show-if-above v-model="leftDrawerOpen" side="left" elevated>

      <q-scroll-area style="height: 50%; margin-top: 100%;">
        <q-list padding class="menu-list">
          <q-item clickable @click="selected = 'home'" :active="selected === 'home'" to="/home" exact v-ripple>
            <q-item-section avatar>
              <q-icon name="home" />
            </q-item-section>

            <q-item-section>
              Home
            </q-item-section>
          </q-item>

          <q-item clickable @click="selected = 'quiz'" :active="selected === 'quiz'" to="/quiz" exact v-ripple>
            <q-item-section avatar>
              <q-icon name="quiz" />
            </q-item-section>

            <q-item-section>
              Quiz
            </q-item-section>
          </q-item>
        </q-list>
      </q-scroll-area>
      <!-- drawer content -->
    </q-drawer>

    <q-drawer show-if-above v-model="rightDrawerOpen" side="right" elevated>
      <!-- drawer content -->
    </q-drawer>

    <q-page-container>
      <router-view/>
    </q-page-container>

    <q-footer elevated className="bg-grey-8 text-white">
      <q-toolbar>
        <q-btn dense flat round icon="menu" @click="toggleLeftDrawer"/>

        <q-toolbar-title>
          <q-avatar>
            <img src="https://cdn.quasar.dev/logo-v2/svg/logo-mono-white.svg">
          </q-avatar>
          Title
        </q-toolbar-title>

        <q-btn dense flat round icon="menu" @click="toggleRightDrawer"/>
      </q-toolbar>
    </q-footer>

  </q-layout>
</template>

<script>
import {defineComponent, ref} from 'vue'

export default defineComponent({
  name: 'MainLayout2',
  setup() {
    const leftDrawerOpen = ref(false)
    const rightDrawerOpen = ref(false)
    const selected = ref('home')

    return {
      leftDrawerOpen,
      toggleLeftDrawer() {
        leftDrawerOpen.value = !leftDrawerOpen.value
      },

      rightDrawerOpen,
      toggleRightDrawer() {
        rightDrawerOpen.value = !rightDrawerOpen.value
      },

      selected
    }
  }
})
</script>
