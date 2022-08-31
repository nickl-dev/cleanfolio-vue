<template>
  <div class="about">
    <header class="about__header">
      <!-- Fill in your name here -->
      <h1 class="about__name">Hi, I'm {Your Name}</h1>
      <div class="about__occupation-wrapper">
        <h2 class="about__occupation">I'm a Developer</h2>
      </div>    
    </header>

    <section class="about__wrapper">
      <div class="about__subwrapper">
        <img :src="personalPicture" alt="Picture of yourself" class="about__image" />
        <div class="about__biowrapper">
          <!-- Replace this text with a short bio about yourself - you may want to adjust size-->
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
// Replace with a link to a photo of yourself which can be stored in the ASSETS folder
import personalPicture from '@/assets/personal-picture.jpg'

export default {
  name: "About",

  data () {
    return {
      // Replace with a link to your resume which can be stored in the PUBLIC folder
      resume: '../resume.pdf',
      personalPicture: personalPicture
    }
  }
}
</script>

<style lang="scss">
@import "@/styles/global.scss";
@keyframes type {
  from {
    width: 0;
  } to {
    width: 100%;
  }
}

.about {
  &__header {
    @include textCenter;
    @include padding5;
    margin-top: 40vh;
  }

  &__name {
    @include name;
  }

  &__occupation {
    &-wrapper {
      display: inline-block
    }
    @include occupation;
    overflow: hidden;
    white-space: nowrap;
    animation: type 1.5s forwards;
  }

  &__wrapper {
    background: $stockBlack;
    padding: 50px $padding5;
    margin-top: 43vh;
    @include tablet {
      padding: 75px $padding5;
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