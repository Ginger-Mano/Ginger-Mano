<template>
  <div class="container">
    <div>
      <h1 class="zoom" style="font-family: Verdana, Geneva, Tahoma, sans-serif">
        manon sainton
      </h1>
      <q-btn
        disable
        class="subheader"
        style="
          font-weight: bolder;
          background-color: rgb(216, 241, 117);
          border-style: solid;
          border-color: black;
          border-width: 3px;
        "
      >
        creative technologist + software engineer
      </q-btn>

      <q-dialog v-model="aboutModal">
        <q-card class="my-card" bordered flat>
          <q-item>
            <q-item-section avatar>
              <q-avatar size="7em">
                <img :src="aboutPic" />
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label
                class="text-h5"
                style="font-weight: bold; color: dodgerblue"
              >
                About Me
              </q-item-label>
            </q-item-section>
            <q-separator></q-separator>
          </q-item>
          <about />

          <q-card-actions align="right">
            <q-btn flat label="OK" color="primary" v-close-popup />
          </q-card-actions>
        </q-card>
      </q-dialog>

      <q-dialog v-model="projectsModal">
        <q-card>
          <q-item>
            <q-item-section avatar>
              <q-avatar rounded size="5em">
                <img :src="projectPic" />
              </q-avatar>
            </q-item-section>

            <q-item-section>
              <q-item-label
                class="text-h5"
                style="font-weight: bold; color: dodgerblue"
              >
                Projects
              </q-item-label>
            </q-item-section>
            <q-separator></q-separator>
          </q-item>
          <projects />

          <q-card-actions align="right">
            <q-btn flat label="OK" color="primary" v-close-popup />
          </q-card-actions>
        </q-card>
      </q-dialog>

      <q-dialog v-model="blogsModal">
        <q-card>
          <q-item>
            <q-item-section avatar>
              <q-avatar rounded size="6em">
                <img :src="blogPic" />
              </q-avatar>
            </q-item-section>

            <q-card-section>
              <q-item-section>
                <q-item-label
                  class="text-h5"
                  style="font-weight: bold; color: dodgerblue"
                >
                  Blogs
                </q-item-label>
              </q-item-section>
            </q-card-section>
          </q-item>
          <blogs />

          <q-card-actions align="right">
            <q-btn flat label="OK" color="primary" v-close-popup />
          </q-card-actions>
        </q-card>
      </q-dialog>
    </div>

    <div class="row" style="align-self: center; justify-content: center">
      <q-list class="rounded-borders" padding separator>
        <q-item class="col-xs-6">
          <q-item-section style="padding: 1em">
            <q-avatar rounded size="7em">
              <img src="https://static.thenounproject.com/png/415376-200.png" />
            </q-avatar>
          </q-item-section>

          <q-item-section style="padding: 1em">
            <q-btn
              class="zoom"
              style="
                background: #ffdede;
                color: black;
                border-style: solid;
                border-color: black;
                border-width: 2px;
              "
              label="About"
              @click="aboutModal = true"
            >
            </q-btn>
          </q-item-section>
        </q-item>

        <q-item>
          <q-item-section style="padding: 1em">
            <q-avatar rounded size="6em">
              <img src="https://static.thenounproject.com/png/12565-200.png" />
            </q-avatar>
          </q-item-section>

          <q-item-section style="padding: 1em">
            <q-btn
              class="zoom"
              style="
                background: #f2b6a0;
                color: black;
                border-style: solid;
                border-color: black;
                border-width: 2px;
              "
              label="Projects"
              @click="projectsModal = true"
            >
            </q-btn>
          </q-item-section>
        </q-item>

        <q-item>
          <q-item-section style="padding: 1em">
            <q-avatar rounded size="7em">
              <img
                src="https://static.thenounproject.com/png/1299097-200.png"
              />
            </q-avatar>
            <q-separator vertical />
          </q-item-section>

          <q-item-section style="padding: 1em">
            <q-btn
              class="zoom"
              style="
                background: #eaa221;
                color: black;
                border-style: solid;
                border-color: black;
                border-width: 2px;
              "
              label="Blogs"
              @click="blogsModal = true"
            >
            </q-btn>
          </q-item-section>
        </q-item>
      </q-list>

      <q-toolbar style="align-self: center; justify-content: center">
        <a :href="gitLink" class="q-pa-md">
          <img :src="gitIcon" class="zoom" />
          <q-tooltip anchor="top middle" class="bg-black">Github</q-tooltip>
        </a>

        <a :href="linkedInLink" class="q-pa-md">
          <img :src="linkedIcon" class="zoom" />
          <q-tooltip anchor="top middle" class="bg-black">LinkedIn</q-tooltip>
        </a>

        <a :href="mediumLink" class="q-pa-md">
          <img :src="mediumIcon" class="zoom" />
          <q-tooltip anchor="top middle" class="bg-black">Medium</q-tooltip>
        </a>

        <a :href="ytLink" class="q-pa-md">
          <img :src="ytIcon" class="zoom" />
          <q-tooltip anchor="top middle" class="bg-black">YouTube</q-tooltip>
        </a>
      </q-toolbar>
    </div>
  </div>
</template>

<script>
import { defineComponent, ref, computed } from "vue";
import About from "components/About.vue";
import Projects from "components/Projects.vue";
import Blogs from "components/Blogs.vue";
import p5 from "p5";

export default defineComponent({
  name: "IndexPage",
  components: { About, Projects, Blogs },
  computed: {
    aboutPic() {
      return process.env.VUE_APP_ABOUT_IMAGE;
    },
    projectPic() {
      return process.env.VUE_APP_PROJECT_IMG;
    },
    blogPic() {
      return process.env.VUE_APP_BLOG_IMG;
    },
    gitIcon() {
      return process.env.VUE_APP_GIT_ICON;
    },
    linkedIcon() {
      return process.env.VUE_APP_LINKED_ICON;
    },
    mediumIcon() {
      return process.env.VUE_APP_MEDIUM_ICON;
    },
    ytIcon() {
      return process.env.VUE_APP_YT_ICON;
    },
    gitLink() {
      return process.env.VUE_APP_GIT;
    },
    linkedInLink() {
      return process.env.VUE_APP_LINKED;
    },
    mediumLink() {
      return process.env.VUE_APP_MEDIUM;
    },
    ytLink() {
      return process.env.VUE_APP_YT;
    },
  },
  setup() {
    const aboutModal = ref(false);
    const projectsModal = ref(false);
    const blogsModal = ref(false);
    let canvas;

    let myp5 = new p5((sketch) => {
      let w = window.innerWidth;
      let h = window.innerHeight;
      let speed = 3;
      let ballPos1 = w;
      let ballPos2 = 0;
      let t;

      sketch.setup = () => {
        canvas = sketch.createCanvas(w, h);
        canvas.style("z-index", "-1");
        canvas.position(0, 0);
        t = 0;
      };

      sketch.draw = () => {
        sketch.background(0, 0);
        let lane1;
        let lane2;

        if (ballPos1 && ballPos2 > 0 + 200 && ballPos1 && ballPos2 < w - 200) {
          lane1 = sketch.random(h) * sketch.noise(t + 5);
          lane2 = sketch.random(h) * sketch.noise(t + 50);
        } else {
          lane1 = h * sketch.noise(t + 5);
          lane2 = h * sketch.noise(t + 50);
        }

        sketch.noStroke();
        sketch.ellipse(ballPos1, lane1, 20, 20);
        sketch.fill(232, 70, 51, 130);
        ballPos1 -= speed;
        t += 0.015;

        sketch.ellipse(ballPos2, lane2, 10, 10);
        sketch.fill(sketch.random(255), sketch.random(229), 229, 130);
        ballPos2 += speed;

        sketch.frameRate(20);

        if (ballPos1 < 0) {
          ballPos1 = w;
        }

        if (ballPos2 > w) {
          ballPos2 = 0;
        }
      };
    });

    return {
      aboutModal,
      projectsModal,
      blogsModal,
      myp5,
    };
  },
});
</script>

<style>
.zoom {
  transition: transform 0.2s;
}

.zoom:hover {
  transform: scale(1.2);
}

.subheader:hover {
  color: indigo;
}

.container {
  margin-top: 0;
  text-align: center;
  position: relative;
  z-index: 2;
}
</style>
