<template>
  <div class="about">
    <header class="about__header">
      <!-- Fill in your name here -->
      <h1 class="about__name">Hi, I'm {Your Name}</h1>
      <vue-typer
        class="about__occupation"
        text="I'm a Developer 🚀"
        :repeat="0"
      >
      </vue-typer>
    </header>

    <section class="about__wrapper">
      <div class="about__subwrapper">
        <img :src="personalPicture" alt="Picture of yourself" class="about__image" />
        <div class="about__biowrapper">
          <!-- Replace this text with a short bio about yourself, may want to adjust size-->
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
// Replace with a link to a photo of yourself which can be stored in the ASSETS folder
import personalPicture from '@/assets/personal-picture.jpg';

export default {
  // Name
  name: "About",

// Components
  components: {
    VueTyper,
  },

  // Data
  data: () => {
    return {
      // Replace with a link to your resume which can be stored in the PUBLIC folder
      resume: '../resume.pdf',
      personalPicture: personalPicture,
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

  &__wrapper {
    background: $stockBlack;
    padding: 50px $padding5;

    @include tablet {
      padding: 75px $padding5;
      margin: 17.5vh 0;
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
