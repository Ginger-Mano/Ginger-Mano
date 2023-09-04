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
            src="https://www.youtube.com/embed/pRNGNh_npa0"
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
              href="https://github.com/Ginger-Mano/Mod2Project"
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
          <q-video
            src="https://www.youtube.com/embed/7xE0sdlucyI"
            loading="lazy"
          >
            The Wildlife Keep
          </q-video>

          <q-inner-loading :showing="visible">
            <q-spinner-gears size="50px" color="grey" />
          </q-inner-loading>

          <q-separator spaced="5px"></q-separator>

          <q-btn class="zoom">
            <a
              href="https://github.com/Ginger-Mano/WildlifeKeep-Frontend2/blob/main/src/App.js"
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
              href="https://github.com/Ginger-Mano/The-Wildlife-Keep-Backend"
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
import { defineComponent, ref } from "vue";

export default defineComponent({
  name: "ProjectsPage",
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
