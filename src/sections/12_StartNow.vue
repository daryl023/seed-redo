<template>
  <div class="main_startnow position-lift limiter">
    <div class="container">
      <div class="col__one">
        <h1>Supercharge your animation workflow</h1>
        <div class="button">
          <button
            onclick="window.open('https://lottielab.io/users/sign_up').focus()"
            class="button__early-access animate-lead full"
          >
            Get early access
            <icon name="arrow" class="arrow" />
          </button>
        </div>
      </div>
      <div class="col__two">
        <img
          loading="lazy"
          class="starnow-image"
          src="@/assets/10_getStarted/startnow-updated.svg"
        />
      </div>
    </div>
  </div>
</template>

<script>
import icon from "@/assets/Icons.vue";

export default {
  name: "StartNow",
  components: {
    icon,
  },
};
</script>

<style lang="scss" scoped>
.main_startnow {
  color: var(--dark);
  padding-top: var(--step-6);
  padding-inline: var(--step-4);
  margin-inline: auto;

  .container {
    display: grid;
    grid-template-columns: 1fr;
    grid-template-rows: 0.5fr max-content;
    grid-auto-columns: 1fr;
    grid-auto-rows: 1fr;
    gap: var(--step-4);
    grid-auto-flow: row;
    justify-items: stretch;
    grid-template-areas:
      "col__one"
      "col__two";
    height: 100%;
  }

  .col__one {
    grid-area: col__one;
    display: flex;
    flex-direction: column;
    gap: var(--step-4);
    h1 {
      font-size: var(--step-2);
      color: white; // white
    }
    .button {
      display: flex;
      flex-direction: column;
      gap: var(--step-0);
      position: relative;
      padding: 4px;
      transition: all 200ms ease-out;
      border-radius: var(--step--1);
      width: fit-content;

      &:hover,
      &:focus-visible {
        transform: scale(0.96);
        backdrop-filter: blur(16px);
      }

      &:active {
        transform: scale(0.85);
        backdrop-filter: blur(16px);
      }

      button {
        border-radius: inherit;
        font-size: var(--step--3);
        line-height: var(--step-0);
        padding-block: var(--step--3);
        padding-inline: var(--step-1);
        transform: none !important;
        display: flex;
        justify-content: center;
        align-items: center;
        gap: var(--step--2);
        .arrow {
          width: 40px !important;
          display: flex;
          stroke: white; // purple

          svg {
            width: 40px !important;
          }
        }
      }

      &:after {
        content: "";
        height: inherit;
        background-image: linear-gradient(
          80deg,
          rgb(122, 111, 251, 0.5) -1%,
          rgb(255, 84, 103, 0.5) 88%,
          rgb(253, 190, 4, 0.5) 100%
        );
        position: absolute;
        z-index: -1;
        top: 0;
        right: 0;
        left: 0;
        bottom: 0;
        border-radius: calc(var(--step-0) - 2px);
        backdrop-filter: blur(16px);
      }
      &__early-access {
        background: rgba(255, 255, 255, 0.1);
        color: #ffffff;
      }
    }
  }

  .col__two {
    grid-area: col__two;
    .starnow-image {
      width: 100%;
      transform: scale(1.2);
    }
  }
}
@media (min-width: 980px) {
  .main_startnow {
    padding-block: var(--step-6);

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
      position: relative;

      .starnow-image {
        width: unset;
        position: absolute;
        left: 0;
        z-index: 1;
        margin-top: var(--step-1);
        margin-left: var(--step-6);
      }
    }
  }
}
</style>
