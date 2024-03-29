<template>
  <div class="meet-lottie position-lift limiter">
    <div class="container">
      <div class="col__one">
        <div class="section__title">
          <h1>The Lottie format</h1>
          <h2 style="color: #007a88">The new standard for motion design</h2>
          <span>
            Lottie is an open-source animation file format that is lighweight,
            high-quality, dynamic and modiefied in real time. Lottie is now used
            to engage consumers and increase conversions by top 500 apps on the
            App Store.</span
          >
          <button
            class="full"
            onclick="window.open('https://airbnb.design/lottie/').focus()"
          >
            Learn more
            <icon name="arrow" class="arrow" />
          </button>
        </div>
      </div>
      <div class="col__two">
        <div class="card card--light card--shadow usecase--ease">
          <div class="sample_container">
            <lottie-animation
              :animationData="
                require('@/assets/09_meetLottie/LottieFormat_Slow.json')
              "
              :loop="true"
              :auto-play="false"
              ref="lottieslow"
              id="lottieslow"
            />
            <!-- <img src="@/assets/ravie/Asset 3.svg" style="width: 100%" /> -->

            <div style="padding-block: var(--step-0)">
              <h3>2.81 MB</h3>
              <span>GIF</span>
            </div>
          </div>
        </div>
        <div class="card card--light card--shadow usecase--ease">
          <div class="sample_container">
            <lottie-animation
              :animationData="
                require('@/assets/09_meetLottie/LottieFormat_Fast.json')
              "
              :loop="true"
              :auto-play="false"
              ref="lottiefast"
              id="lottiefast"
            />
            <!-- <img src="@/assets/ravie/Asset 4.svg" style="width: 100%" /> -->
            <div style="padding-block: var(--step-0)">
              <h3 style="color: #00bcae">28 KB</h3>
              <span style="color: #00bcae">Lottie</span>
            </div>
          </div>
        </div>
      </div>
      <!-- <img
        v-show="!mobile"
        src="@/assets/09_meetLottie/meetlottie-image.svg"
        style="
          position: absolute;
          top: 0;
          right: 0;
          z-index: -1;
          margin-top: -2rem;
          margin-right: -2rem;
          width: 600px;
          height: auto;
        "
      /> -->
    </div>
  </div>
</template>

<script>
import LottieAnimation from "lottie-web-vue";
import icon from "@/assets/Icons.vue";
import checkScreen from "@/mixins/checkScreen";

export default {
  data() {
    return {};
  },
  mixins: [checkScreen],
  components: {
    LottieAnimation,
    icon,
  },
  mounted() {
    this.lottieSlowIntersection();
    this.lottieFastIntersection();
  },
  methods: {
    lottieSlowIntersection() {
      const el = document.querySelector("#lottieslow");
      const observer = new window.IntersectionObserver(
        ([entry]) => {
          entry.boundingClientRect.top;
          if (entry.isIntersecting) {
            this.$refs.lottieslow.play();
            // console.log(`lottieslow play`);
          }
          // if (entry.boundingClientRect.top > 0 && entry.isIntersecting) {
          else {
            // pause animation
            this.$refs.lottieslow.pause();
            // console.log(`lottieslow pause`);
          }
        },
        {
          root: null,
          threshold: 0,
        }
      );
      observer.observe(el);
    },
    lottieFastIntersection() {
      const el = document.querySelector("#lottiefast");
      const observer = new window.IntersectionObserver(
        ([entry]) => {
          entry.boundingClientRect.top;
          if (entry.isIntersecting) {
            this.$refs.lottiefast.play();
            // console.log(`lottiefast play`);
          }
          // if (entry.boundingClientRect.top > 0 && entry.isIntersecting) {
          else {
            // pause animation
            this.$refs.lottiefast.pause();
            // console.log(`lottiefast pause`);
          }
        },
        {
          root: null,
          threshold: 0,
        }
      );
      observer.observe(el);
    },
  },
};
</script>

<style lang="scss" scoped>
.meet-lottie {
  color: var(--primary);
  margin: auto;
  overflow: hidden;
  padding: var(--step-4);

  .sample_container {
    width: fit-content;
    height: fit-content;
  }

  .container {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: auto;
    grid-auto-columns: 1fr;
    grid-auto-rows: 1fr;
    gap: var(--step-0);
    grid-auto-flow: row;
    justify-items: stretch;
    grid-template-areas:
      "col__one"
      "col__two";
  }

  .col__one {
    grid-area: col__one;
    display: flex;
    flex-direction: column;
    justify-content: center;
    gap: var(--step--1);
    .section__title {
      h1 {
        color: #00bcae;
      }
      h2 {
        width: 90%;
        color: var(--dark-sub);
        font-weight: var(--medium);
      }
      span {
        color: var(--dark);
        width: 100%;
        line-height: var(--step-0);
      }
      button {
        gap: var(--step--4);
        align-items: center;
        height: max-content;
        color: #00bcae;

        .arrow {
          width: 40px !important;
          display: flex;
          stroke: #00bcae;

          svg {
            width: 40px !important;
          }
        }
      }
    }
  }

  .col__two {
    grid-area: col__two;
    display: flex;
    gap: var(--step-0);
    height: fit-content;
    .card {
      padding: 0 !important;
    }

    div {
      display: flex;
      flex-direction: column;
      align-items: center;
      height: max-content;
      h3 {
        font-size: var(--step-0);
      }
      span {
        font-weight: var(--medium);
        font-size: var(--step-0);
      }
    }
  }
}
@media (min-width: 980px) {
  .meet-lottie {
    .section__title {
      span {
        width: 80%;
      }
    }
    .container {
      display: grid;
      grid-template-columns: 1fr 1fr;
      grid-template-rows: 1fr;
      grid-auto-columns: 1fr;
      grid-auto-rows: 1fr;
      gap: var(--step-0);
      grid-auto-flow: row;
      justify-items: stretch;
      grid-template-areas: "col__one col__two";
      height: 100%;
    }

    .col__two {
      grid-area: col__two;
      display: flex;
      align-items: center;
    }
  }
}
</style>
