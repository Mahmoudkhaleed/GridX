<template>
  <q-page class="row" style="padding: 50px 0">
    <div
      class="q-px-md q-mx-auto"
      :class="{
        'col-12': $q.screen.xs || $q.screen.width <= 600 || $q.screen.sm,
        'col-11': $q.screen.md,
        'col-9': $q.screen.lg,
        'col-8': $q.screen.xl,
      }"
    >
      <div class="row q-mb-lg no-wrap-sm wrap-lg" style="gap: 20px">
        <div
          class="flex items-center bg-white no-wrap q-pa-xl relative-position"
          :class="{
            'col-12': $q.screen.width <= 994,
            col: $q.screen.width > 994,
          }"
          style="border-radius: 40px; transition: all 0.3s"
          :style="`${
            isHovering ? 'box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);' : ''
          }`"
          @mouseenter="isHovering = true"
          @mouseleave="isHovering = false"
        >
          <div
            class="box overflow-hidden q-mr-md flex justify-center items-center"
            style="border-radius: 20px 0; background-color: blue"
          >
            <q-img
              src="~assets/me.png"
              spinner-color="white"
              spinner-size="30px"
              style="width: 300px"
            />
          </div>
          <div>
            <div class="hint text-grey-5 text-bold q-mb-sm text-uppercase">
              A Web Designer
            </div>
            <div
              class="name text-capitalize"
              style="font-size: 40px; line-height: 1"
            >
              mahmoud khaled
            </div>
            <div class="text-capitalize text-grey-5 text-subtitle1">
              i am a web designer base in Egypt
            </div>
          </div>
          <q-btn
            class="absolute"
            flat
            color="white"
            unelevated
            style="bottom: 15px; right: 15px"
          >
            <q-icon color="grey" size="30px" name="mdi-arrow-right-thin" />
          </q-btn>
        </div>
        <div
          class="flex content-start"
          :class="{
            'col-12': $q.screen.width <= 994,
            col: $q.screen.width > 994,
          }"
          style="gap: 20px"
        >
          <div
            class="bg-white q-pa-sm col-shrink q-px-md full-width"
            style="border-radius: 999px; height: fit-content"
          >
            <div class="text-no-wrap overflow-auto captions">
              <span v-for="n in 3" :key="n" class="text-uppercase text-grey-5">
                last works and <span class="text-primary">features </span>
                {{ n < 3 ? "*" : "" }}
              </span>
            </div>
          </div>
          <div class="row full-width" style="gap: 20px">
            <BoxWithImageAndTitle
              class="col"
              hint="more about me"
              nameTitle="crendential"
              link="home"
            >
              <template v-slot:image>
                <q-img
                  src="~assets/sign.png"
                  spinner-color="primary"
                  spinner-size="30px"
                  width="100%"
                />
              </template>
            </BoxWithImageAndTitle>
            <BoxWithImageAndTitle
              class="col"
              hint="showcase"
              nameTitle="projects"
              link="home"
            >
              <template v-slot:image>
                <q-img
                  src="~assets/my-works.png"
                  spinner-color="primary"
                  spinner-size="30px"
                  width="100%"
                />
              </template>
            </BoxWithImageAndTitle>
          </div>
        </div>
      </div>
      <div
        class="row q-mb-md"
        :class="{
          'no-wrap': $q.screen.width > 994,
        }"
        style="gap: 20px"
      >
        <BoxWithImageAndTitle
          class="col"
          hint="blogs"
          nameTitle="GFonts"
          link="home"
        >
          <template v-slot:image>
            <q-img
              src="~assets/gfonts.png"
              spinner-color="primary"
              spinner-size="30px"
              width="100%"
            />
          </template>
        </BoxWithImageAndTitle>

        <BoxWithImageAndTitle
          :class="{
            'order-last col-12': $q.screen.width <= 994,
            'col-6': $q.screen.width > 994,
          }"
          hint="specialization"
          nameTitle="services offerings"
          link="home"
        >
          <template v-slot:image>
            <div class="row full-width" style="height: 130px">
              <div class="col-3 flex justify-center items-center">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  stroke-width="1.5"
                  viewBox="0 0 24 24"
                  fill="none"
                  style="width: 60px"
                  class="text-primary"
                >
                  <path
                    d="M2 19V9C2 7.89543 2.89543 7 4 7H4.5C5.12951 7 5.72229 6.70361 6.1 6.2L8.32 3.24C8.43331 3.08892 8.61115 3 8.8 3H15.2C15.3889 3 15.5667 3.08892 15.68 3.24L17.9 6.2C18.2777 6.70361 18.8705 7 19.5 7H20C21.1046 7 22 7.89543 22 9V19C22 20.1046 21.1046 21 20 21H4C2.89543 21 2 20.1046 2 19Z"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M12 17C14.2091 17 16 15.2091 16 13C16 10.7909 14.2091 9 12 9C9.79086 9 8 10.7909 8 13C8 15.2091 9.79086 17 12 17Z"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                </svg>
              </div>
              <div class="col-3 flex justify-center items-center">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  style="width: 60px"
                  class="text-primary"
                  stroke-width="1.5"
                  viewBox="0 0 24 24"
                  fill="none"
                >
                  <path
                    d="M12 14.5C15.3137 14.5 18 11.8137 18 8.5C18 5.18629 15.3137 2.5 12 2.5C8.68629 2.5 6 5.18629 6 8.5C6 11.8137 8.68629 14.5 12 14.5Z"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M16 21.5C19.3137 21.5 22 18.8137 22 15.5C22 12.1863 19.3137 9.5 16 9.5C12.6863 9.5 10 12.1863 10 15.5C10 18.8137 12.6863 21.5 16 21.5Z"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M8 21.5C11.3137 21.5 14 18.8137 14 15.5C14 12.1863 11.3137 9.5 8 9.5C4.68629 9.5 2 12.1863 2 15.5C2 18.8137 4.68629 21.5 8 21.5Z"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                </svg>
              </div>
              <div class="col-3 flex justify-center items-center">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  viewBox="0 0 24 24"
                  stroke-width="1.5"
                  fill="none"
                  style="width: 60px"
                  class="text-primary"
                >
                  <path
                    d="M12 19.01L12.01 18.9989"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M18 18V21.4C18 21.7314 17.7314 22 17.4 22H6.6C6.26863 22 6 21.7314 6 21.4V18"
                    stroke="currentColor"
                    stroke-linecap="round"
                  />
                  <path
                    d="M18 6V2.6C18 2.26863 17.7314 2 17.4 2H6.6C6.26863 2 6 2.26863 6 2.6V6"
                    stroke="currentColor"
                    stroke-linecap="round"
                  />
                  <path
                    d="M15.5 8.5L19 12L15.5 15.5"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M8.5 8.5L5 12L8.5 15.5"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                </svg>
              </div>
              <div class="col-3 flex justify-center items-center">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  stroke-width="1.5"
                  viewBox="0 0 24 24"
                  fill="none"
                  style="width: 60px"
                  class="text-primary"
                >
                  <path
                    d="M12 2C6.47715 2 2 6.47715 2 12C2 17.5228 6.47715 22 12 22C17.5228 22 22 17.5228 22 12C22 6.47715 17.5228 2 12 2Z"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M8 21.1679V14L12 7L16 14V21.1679"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M8 14C8 14 9.12676 15 10 15C10.8732 15 12 14 12 14C12 14 13.1268 15 14 15C14.8732 15 16 14 16 14"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                </svg>
              </div>
            </div>
          </template>
        </BoxWithImageAndTitle>
        <BoxWithImageAndTitle
          class="col"
          hint="blogs"
          nameTitle="GFonts"
          link="home"
        >
          <template v-slot:image>
            <div
              class="row full-width bg-grey-1"
              style="height: 130px; border-radius: 30px"
            >
              <div class="col-6 flex justify-center items-center">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  stroke-width="1.5"
                  viewBox="0 0 24 24"
                  fill="none"
                  style="width: 60px"
                  class="text-primary"
                >
                  <path
                    d="M2 12C2 17.5228 6.47715 22 12 22C17.5228 22 22 17.5228 22 12C22 6.47715 17.5228 2 12 2C6.47715 2 2 6.47715 2 12Z"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M16.6726 20.8435C15.5 14 12.5 8.00003 8.5 2.62964"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M2.06653 10.8406C6.00004 11 15.2829 10.5 19.1415 5"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                  <path
                    d="M21.9677 12.81C15.3438 10.8407 7.50002 14.0001 5.23145 19.3613"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                </svg>
              </div>
              <div class="col-6 flex justify-center items-center">
                <svg
                  xmlns="http://www.w3.org/2000/svg"
                  stroke-width="1.5"
                  viewBox="0 0 24 24"
                  fill="none"
                  style="width: 60px"
                  class="text-primary"
                >
                  <path
                    d="M23 3.01006C23 3.01006 20.9821 4.20217 19.86 4.54006C19.2577 3.84757 18.4573 3.35675 17.567 3.13398C16.6767 2.91122 15.7395 2.96725 14.8821 3.29451C14.0247 3.62177 13.2884 4.20446 12.773 4.96377C12.2575 5.72309 11.9877 6.62239 12 7.54006V8.54006C10.2426 8.58562 8.50127 8.19587 6.93101 7.4055C5.36074 6.61513 4.01032 5.44869 3 4.01006C3 4.01006 -1 13.0101 8 17.0101C5.94053 18.408 3.48716 19.109 1 19.0101C10 24.0101 21 19.0101 21 7.51006C20.9991 7.23151 20.9723 6.95365 20.92 6.68006C21.9406 5.67355 23 3.01006 23 3.01006Z"
                    stroke="currentColor"
                    stroke-linecap="round"
                    stroke-linejoin="round"
                  />
                </svg>
              </div>
            </div>
          </template>
        </BoxWithImageAndTitle>
      </div>
      <div
        class="row"
        :class="{
          'no-wrap': $q.screen.width > 994,
        }"
        style="gap: 20px"
      >
        <BoxWithImageAndTitle
          :class="{
            'col-12': $q.screen.width <= 994,
            col: $q.screen.width > 994,
          }"
          link="home"
        >
          <template v-slot:image>
            <div class="row full-width" style="height: 140px">
              <div class="col-4 column justify-center items-center">
                <div class="num text-primary" style="font-size: 45px">07</div>
                <div
                  class="hint text-uppercase text-bold text-grey-5 text-center"
                >
                  years <br />
                  experience
                </div>
              </div>
              <div class="col-4 column justify-center items-center">
                <div class="num text-primary" style="font-size: 45px">+125</div>
                <div
                  class="hint text-uppercase text-bold text-grey-5 text-center"
                >
                  clients <br />
                  worldwide
                </div>
              </div>
              <div class="col-4 column justify-center items-center">
                <div class="num text-primary" style="font-size: 45px">+210</div>
                <div
                  class="hint text-uppercase text-bold text-grey-5 text-center"
                >
                  total <br />
                  projects
                </div>
              </div>
            </div>
          </template>
        </BoxWithImageAndTitle>
        <BoxWithImageAndTitle
          :class="{
            'col-12': $q.screen.width <= 994,
            col: $q.screen.width > 994,
          }"
          link="home"
        >
          <template v-slot:image>
            <div
              class="full-width flex justify-between items-end"
              style="height: 140px"
            >
              <div
                style="font-size: 45px; line-height: 1.2"
                class="text-capitalize"
              >
                let's<br />
                work <span class="text-primary">together</span>
              </div>
              <q-btn
                flat
                color="white"
                unelevated
                style="right: -10px"
                :to="{ name: 'home' }"
              >
                <q-icon color="grey" size="30px" name="mdi-arrow-right-thin" />
              </q-btn>
            </div>
          </template>
        </BoxWithImageAndTitle>
      </div>
    </div>
  </q-page>
</template>

<script setup>
import { ref } from "vue";
import BoxWithImageAndTitle from "src/components/index/BoxWithImageAndTitle.vue";
import { useQuasar } from "quasar";

const $q = useQuasar();

const isHovering = ref(false);
defineOptions({
  name: "IndexPage",
});
</script>
<style lang="scss">
.captions::-webkit-scrollbar {
  display: none;
}
</style>
