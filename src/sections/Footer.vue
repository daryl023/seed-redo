<script>
import icon from "@/assets/Icons.vue";

export default {
  name: "Footer",
  data() {
    return {};
  },
  components: {
    icon,
  },
};
</script>

<template>
  <div class="footer position-lift limiter">
    <div class="first-section">
      <div
        class="upper-links"
        style="
          display: flex;
          gap: var(--step--4);
          flex-direction: column;
          align-items: flex-start;
        "
      >
        <div>
          <router-link to="/"> <icon name="logo" class="logo" /></router-link>
          <router-link class="header-link" to="/" id="nav_link"
            >LottieLab</router-link
          >
        </div>
        <div class="socials" style="display: flex">
          <router-link to="/twitter">
            <icon name="twitter" class="logo"
          /></router-link>
          <router-link to="/instagram">
            <icon name="instagram" class="logo"
          /></router-link>
          <router-link to="/community">
            <icon name="discord" class="logo"
          /></router-link>
          <router-link to="/linkedin">
            <icon name="linkedin" class="logo"
          /></router-link>
        </div>
        <span style="color: #585858"
          >© 2022 LottieLab Ltd. <br />
          All rights reserved.</span
        >
      </div>
    </div>
    <div class="links">
      <!-- <div>
        <router-link class="header-link" to="/" id="nav_link"
          >Usecases</router-link
        >
        <a href="/">Icon Animation</a>
        <a href="/">Website Hero</a>
        <a href="/">Onboarding</a>
        <a href="/">Progression</a>
        <a href="/">Agencies</a>
        <a href="/">Templates</a>
      </div> -->
      <div>
        <router-link class="header-link" to="/" id="nav_link"
          >Resources</router-link
        >
        <a href="https://medium.com/lottielab" target="_blank">Blog</a>
        <a href="https://discord.com/invite/NDUBtvg95a" target="_blank"
          >Join our Community</a
        >
        <a href="https://airbnb.design/lottie/" target="_blank"
          >What is Lottie?</a
        >
      </div>
      <div>
        <router-link class="header-link" to="/" id="nav_link"
          >Company</router-link
        >
        <a
          href="https://lottielab.notion.site/Careers-b4f40799d8294be9ab1c910b881cf6ca"
          target="_blank"
          >Join Us</a
        >
        <a href="/">Privacy Policy</a>
        <a href="/">Terms of Use</a>
        <a href="/">Contact Us</a>
      </div>
    </div>
  </div>
</template>

<style lang="scss" scoped>
.footer {
  color: var(--primary);
  padding-inline: var(--step-4);
  padding-block: var(--step-6);
  display: flex;
  flex-direction: column-reverse;
  gap: var(--step-0);
  justify-content: space-between;
  margin: auto;

  .header-link {
    font-size: var(--step--1);
    font-weight: var(--semi-bold);
    color: var(--primary);
  }

  .links {
    display: flex;
    flex-direction: row;
    gap: var(--step-4);
    text-align: start;

    div {
      display: flex;
      flex-direction: column;
      gap: var(--step--1);
      align-items: flex-start;
      a:not(:first-child) {
        color: white;
        font-size: var(--step--4);
      }
    }
  }

  & > div {
    flex-direction: column;
    gap: var(--step--2);
    flex-wrap: wrap;
  }

  & > div > div {
    display: flex;
    align-items: center;

    .logo {
      color: var(--dark);
      width: var(--step-2);
    }
  }
}
@media (min-width: 980px) {
  .footer {
    color: var(--primary);
    padding-inline: var(--step-4);
    padding-block: var(--step-6);
    display: flex;
    flex-direction: row;
    gap: var(--step-0);
    justify-content: space-between;
    margin: auto;

    .header-link {
      font-size: var(--step--1);
      font-weight: var(--semi-bold);
      color: var(--primary);
    }

    .links {
      display: flex;
      flex-direction: row;
      gap: var(--step-4);
      text-align: start;

      div {
        display: flex;
        flex-direction: column;
        gap: var(--step--1);
        align-items: flex-start;
        a:not(:first-child) {
          color: white;
          font-size: var(--step--4);
        }
      }
    }

    & > div {
      display: flex;
      flex-direction: column;
      gap: var(--step--2);
    }

    & > div > div {
      display: flex;
      align-items: center;
      // gap: var(--step-0);

      .logo {
        color: var(--dark);
        width: var(--step-2);
      }
    }
  }
}
</style>
