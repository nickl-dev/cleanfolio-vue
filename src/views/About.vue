<template>
  <div class="about">
    <header class="about__header">
      <h1 class="about__name">Hi, I'm {Your Name}</h1>
      <vue-typer
        class="about__occupation"
        text="I'm a Developer 🚀"
        :repeat="0"
      >
      </vue-typer>
    </header>
    <div class="about__current">
      <h2 class="about__job">Currently: {Job Title} @</h2>
      <a :href="companyLink" target="_blank">
        <img class="about__employer" :src="companyLogo" />
      </a>
    </div>
    <section class="about__wrapper">
      <div class="about__subwrapper">
        <img :src="candid" alt="Candid photo of yourself" class="about__image" />
        <div class="about__biowrapper">
          <p class="about__bio">
            Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
          </p>
          <a
            :href="resume"
            class="about__resume"
            target="_blank"
          >
          Resume
          </a>
        </div>
      </div>
    </section>
  </div>
</template>

<script>
import { VueTyper } from "vue-typer";
import candid from '@/assets/candid.jpg';
import companyLogo from '@/assets/company-logo.png'

export default {
  name: "About",

  components: {
    VueTyper,
  },

  data: () => {
    return {
      resume: '../nick-lal-resume.pdf',
      candid: candid,
      companyLogo: companyLogo
    };
  },
};
</script>

<style lang="scss">
@import "@/styles/global.scss";

.about {
  &__header {
    @include textCenter;
    @include padding5;
    margin: 35vh 0;
  }

  &__name {
    @include name;
  }

  &__occupation {
    @include occupation;
  }

  &__current {
    @include textCenter;
    @include padding5;
    margin: 50vh 0;
  }

  &__job {
    font-weight: 600;
    font-size: $font20;
  }

  &__employer {
    width: 100px;

    @include tablet {
      width: 150px;
    }

    @include desktop {
      width: 200px;
    }
  }

  &__wrapper {
    background: $stockBlack;
    padding: 50px $padding5;

    @include tablet {
      padding: 75px $padding5;
      margin: 20vh 0;
    }

    @include desktop {
      padding: 100px 13%;
    }
  }

  &__subwrapper {
    @include textCenter;

    @include tablet {
      @include flexCenter;
      justify-content: space-evenly;
    }
  }

  &__biowrapper {
    max-width: 550px;
    margin: auto;

    @include tablet {
      width: 50%;
    }
  }

  &__image {
    @include headshot;
  }

  &__bio {
    @include bio;
  }

  &__resume {
    @include button;
    font-size: $font20;
    display: inline-block;

    &:hover {
      @include invertToWhite;
    }
  }
}
</style>
