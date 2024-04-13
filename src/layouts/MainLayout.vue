<template>
  <q-layout view="lhh LpR lff" style="background-color: #f7f9fc">
    <main-header @close="leftDrawerOpen = !leftDrawerOpen" />
    <q-drawer
      v-model="leftDrawerOpen"
      side="left"
      overlay
      behavior="mobile"
      bordered
      v-if="$q.screen.width < 600"
    >
      <main-drawer />
    </q-drawer>
    <q-page-container>
      <router-view />
    </q-page-container>
    <q-footer class="bg-transparent">
      <q-toolbar
        class="flex justify-center text-dark"
        style="padding: 100px 20px"
      >
        <div class="column items-center">
          <q-btn flat class="q-mb-lg" color="white">
            <div
              class="text-bold"
              style="font-size: x-large; text-transform: capitalize"
            >
              <span class="text-dark">Grid</span
              ><span class="text-primary">X</span>
            </div>
          </q-btn>
          <q-btn-group
            flat
            class="text-dark text-grey-8 q-mb-lg"
            style="font-size: large"
          >
            <q-btn flat label="home" style="text-transform: capitalize" />
            <q-btn flat label="About" style="text-transform: capitalize" />
            <q-btn flat label="Works" style="text-transform: capitalize" />
            <q-btn flat label="contact" style="text-transform: capitalize" />
          </q-btn-group>
          <div class="copyrights text-grey-8 text-center">
            {{ new Date().getFullYear() }} &copy; Made with love by
            <a
              href="https://mk-pro.netlify.com"
              class="text-primary"
              style="text-decoration: underline dashed"
              target="_blank"
              >Mahmoud Khaled</a
            >
          </div>
        </div>
      </q-toolbar>
    </q-footer>
  </q-layout>
</template>

<script setup>
import { ref } from "vue";
import { useQuasar } from "quasar";
import MainHeader from "../components/main/MainHeader.vue";
import MainDrawer from "../components/main/MainDrawer.vue";

const leftDrawerOpen = ref(false);

const $q = useQuasar();
defineOptions({
  name: "MainLayout",
});
</script>

<style lang="scss">
.router-link-active.router-link-exact-active {
  color: $primary !important;
}
</style>
