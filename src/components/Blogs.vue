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
              href="https://medium.com/javascript-in-plain-english/applying-basic-destructuring-in-react-ede119aab03e"
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
              href="https://mcasimirian.medium.com/a-brief-intro-to-color-theory-f25fd3479bd2"
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
              href="https://mcasimirian.medium.com/the-basics-of-using-jsx-in-react-js-578db41ec625"
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
              href="https://mcasimirian.medium.com/5-tips-for-creatives-navigating-a-coding-bootcamp-58b2e19bbcf0"
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
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "BlogsPage",
  setup() {
    const visible = ref(false);
    const showSimulatedReturnData = ref(false);

    return {
      visible,
      showSimulatedReturnData,

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
