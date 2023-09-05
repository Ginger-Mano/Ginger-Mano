<template>
  <div
    class="q-pa-md row items-start q-gutter-md"
    style="position: relative; align-self: center; justify-content: center"
    align="center"
  >
    <q-card class="q-pa-md" style="width: 100%" bordered>
      <q-card-section>
        <div class="text-h6">
          <q-video
            :src="spotzLink"
            loading="lazy"
            @vnode-mounted="showTextLoading"
          >
            Spotz
          </q-video>

          <q-inner-loading :showing="visible">
            <q-spinner-gears size="50px" color="grey" />
          </q-inner-loading>

          <q-separator spaced="5px"></q-separator>

          <q-btn class="zoom">
            <a
              :href="spotzGit"
              style="
                text-decoration: none;
                color: black;
                font-family: Verdana, Geneva, Tahoma, sans-serif;
                font-weight: bold;
              "
            >
              GitHub</a
            >
          </q-btn>
        </div>
      </q-card-section>
    </q-card>

    <q-card class="q-pa-md" style="width: 100%" bordered>
      <q-card-section>
        <div class="text-h6">
          <q-video :src="wildLink" loading="lazy"> The Wildlife Keep </q-video>

          <q-inner-loading :showing="visible">
            <q-spinner-gears size="50px" color="grey" />
          </q-inner-loading>

          <q-separator spaced="5px"></q-separator>

          <q-btn class="zoom">
            <a
              :href="wildFront"
              style="
                text-decoration: none;
                color: black;
                font-family: Verdana, Geneva, Tahoma, sans-serif;
                font-weight: bold;
              "
            >
              Front-End
            </a>
          </q-btn>
          &nbsp;
          <q-btn class="zoom">
            <a
              :href="wildBack"
              style="
                text-decoration: none;
                color: black;
                font-family: Verdana, Geneva, Tahoma, sans-serif;
                font-weight: bold;
              "
            >
              Back-End
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
  name: "ProjectsPage",
  computed: {
    wildLink() {
      return process.env.VUE_APP_WILDLIFE;
    },
    spotzLink() {
      return process.env.VUE_APP_SPOTZ;
    },
    spotzGit() {
      return process.env.VUE_APP_SPOTZ_GIT;
    },
    wildFront() {
      return process.env.VUE_APP_WILD_FRONT;
    },
    wildBack() {
      return process.env.VUE_APP_WILD_BACK;
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
