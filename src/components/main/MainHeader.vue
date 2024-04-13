<template>
  <q-header style="background-color: #f7f9fc">
    <q-toolbar class="row q-py-md">
      <div
        class="q-px-md q-mx-auto"
        :class="{
          'col-12': $q.screen.xs || $q.screen.width <= 600 || $q.screen.sm,
          'col-11': $q.screen.md,
          'col-9': $q.screen.lg,
          'col-8': $q.screen.xl,
        }"
      >
        <div class="flex justify-between items-center full-width">
          <q-btn flat>
            <div
              class="text-bold"
              style="font-size: xx-large; text-transform: capitalize"
            >
              <span class="text-dark">Grid</span
              ><span class="text-primary">X</span>
            </div>
          </q-btn>
          <div
            class="flex text-dark text-grey-8"
            style="gap: 30px; font-size: medium"
            v-if="$q.screen.width >= 600"
          >
            <router-link
              class="text-grey-8"
              style="text-transform: capitalize; text-decoration: none"
              :to="{ name: 'home' }"
              >home</router-link
            >
            <router-link
              class="text-grey-8"
              style="text-transform: capitalize; text-decoration: none"
              :to="{ name: 'about' }"
              >About</router-link
            >
            <router-link
              class="text-grey-8"
              style="text-transform: capitalize; text-decoration: none"
              :to="{ name: 'works' }"
              >Works</router-link
            >
            <router-link
              class="text-grey-8"
              style="text-transform: capitalize; text-decoration: none"
              :to="{ name: 'contact' }"
              >contact</router-link
            >
          </div>
          <q-btn
            push
            v-if="$q.screen.width >= 600"
            aria-label="Let's Talk"
            style="text-transform: capitalize; background-color: #323232"
            >Let's talk</q-btn
          >
          <q-btn
            push
            v-if="$q.screen.width < 600"
            icon="mdi-menu"
            round
            style="text-transform: capitalize; background-color: #323232"
            @click="$emit('close')"
          ></q-btn>
        </div>
      </div>
    </q-toolbar>
  </q-header>
</template>

<script>
export default {
  name: "MainHeader",
};
</script>

<style lang="scss" scoped></style>
