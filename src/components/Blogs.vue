<template>
  <div
    class="q-pa-md row items-start q-gutter-md"
    style="position: relative; align-self: center; justify-content: center"
    align="center"
  >
    <q-card class="q-pa-md" style="width: 100%" bordered>
      <q-img
        alt=""
        src="https://miro.medium.com/max/1600/1*-ezOyzYWgZnBHJ7p-qT43A.gif"
      />

      <q-inner-loading :showing="visible">
        <q-spinner-gears size="50px" color="grey" />
      </q-inner-loading>

      <q-card-section>
        <div class="text-h6">
          <q-btn class="zoom">
            <a
              :href="destructureLink"
              style="
                text-decoration: none;
                font-weight: bold;
                color: black;
                font-family: Verdana, Geneva, Tahoma, sans-serif;
              "
            >
              Applying Basic Destructuring in React
            </a>
          </q-btn>
        </div>
      </q-card-section>
    </q-card>

    <q-card class="q-pa-md" style="width: 100%" bordered>
      <q-img
        alt=""
        src="https://miro.medium.com/max/1000/1*xaSydwj9PfrrdV1DSFfH8w.gif"
      />

      <q-inner-loading :showing="visible">
        <q-spinner-gears size="50px" color="grey" />
      </q-inner-loading>

      <q-card-section>
        <div class="text-h6">
          <q-btn class="zoom">
            <a
              :href="colorLink"
              style="
                text-decoration: none;
                font-weight: bold;
                color: black;
                font-family: Verdana, Geneva, Tahoma, sans-serif;
              "
            >
              A Brief. Intro to Color Theory
            </a>
          </q-btn>
        </div>
      </q-card-section>
    </q-card>

    <q-card class="q-pa-md" style="width: 100%" bordered>
      <q-img
        alt=""
        src="https://miro.medium.com/max/960/1*jcyp66zO_oLOAZbTY4a-vQ.gif"
      />

      <q-inner-loading :showing="visible">
        <q-spinner-gears size="50px" color="grey" />
      </q-inner-loading>

      <q-card-section>
        <div class="text-h6">
          <q-btn class="zoom">
            <a
              :href="jsxLink"
              style="
                text-decoration: none;
                color: black;
                font-weight: bold;
                font-family: Verdana, Geneva, Tahoma, sans-serif;
              "
            >
              The Basics of JSX in React.js
            </a>
          </q-btn>
        </div>
      </q-card-section>
    </q-card>

    <q-card class="q-pa-md" style="width: 100%" bordered>
      <q-img
        alt=""
        src="https://miro.medium.com/max/700/1*-VKOD5WrqdjNxIJy7C0_iw.gif"
      />

      <q-inner-loading :showing="visible">
        <q-spinner-gears size="50px" color="grey" />
      </q-inner-loading>

      <q-card-section>
        <div class="text-h6">
          <q-btn class="zoom">
            <a
              :href="creativesLink"
              style="
                text-decoration: none;
                color: black;
                font-weight: bold;
                font-family: Verdana, Geneva, Tahoma, sans-serif;
              "
            >
              5 Tips for Creatives Navigating a Coding Bootcamp
            </a>
          </q-btn>
        </div>
      </q-card-section>
    </q-card>
  </div>
</template>

<script lang="ts">
import { defineComponent, ref, computed } from "vue";

export default defineComponent({
  name: "BlogsPage",
  computed: {
    destructureLink() {
      return process.env.VUE_APP_DESTRUCTURING;
    },
    colorLink() {
      return process.env.VUE_APP_COLOR;
    },
    jsxLink() {
      return process.env.VUE_APP_JSX;
    },
    creativesLink() {
      return process.env.VUE_APP_CREATIVES;
    },
  },
  setup() {
    const visible = ref(false);
    const showSimulatedReturnData = ref(false);

    return {
      visible,
      showSimulatedReturnData,
      computed,

      showTextLoading() {
        visible.value = true;
        showSimulatedReturnData.value = false;

        setTimeout(() => {
          visible.value = false;
          showSimulatedReturnData.value = true;
        }, 1000);
      },
    };
  },
});
</script>
