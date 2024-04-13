<template>
  <div
    class="flex justify-center items-start bg-white q-pa-lg"
    style="border-radius: 40px; transition: all 0.3s"
    :style="`${isHovering ? 'box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);' : ''}`"
    @mouseenter="isHovering = true"
    @mouseleave="isHovering = false"
  >
    <div class="row full-width">
      <slot name="image"></slot>
    </div>
    <div class="row full-width q-mt-xl" v-if="hint">
      <div class="hint text-grey-5 text-bold q-mb-sm text-uppercase">
        {{ hint }}
      </div>
    </div>
    <div class="row full-width" v-if="nameTitle">
      <div
        class="text-black full-width flex justify-between no-wrap text-capitalize"
        style="font-size: x-large"
      >
        <span>{{ nameTitle }}</span>
        <q-btn
          flat
          color="white"
          unelevated
          style="right: -10px"
          :to="{ name: link }"
        >
          <q-icon color="grey" size="30px" name="mdi-arrow-right-thin" />
        </q-btn>
      </div>
    </div>
  </div>
</template>

<script>
import { ref } from "vue";

export default {
  name: "BoxWithImageAndTitle",
  setup() {
    const isHovering = ref(false);
    return {
      isHovering,
    };
  },
  props: {
    hint: String,
    nameTitle: String,
    link: String,
  },
};
</script>

<style lang="scss" scoped></style>
