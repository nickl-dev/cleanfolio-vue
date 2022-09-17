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
        <img 
          :src="personalPicture" 
          alt="Picture of yourself" 
          class="about__image" 
          loading="lazy"
        />
        <div class="about__biowrapper">
          <!-- Replace this text with a short bio about yourself -->
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
// Replace with a photo of yourself which can be stored in @/assets
import personalPicture from '@/assets/personal-picture.jpg'

export default {
  name: "About",

  data () {
    return {
      // Replace with a link to your resume which can be stored in /public
      resume: '../resume.pdf',
      personalPicture: personalPicture
    }
  }
}
</script>

<style lang="scss">
@import "@/styles/global.scss";

@keyframes type {
  from { width: 0; }
  to { width: 100%; }
}

.about {
  &__header {
    @include padding5;
    text-align: center;
    margin-top: 40vh;
  }

  &__name {
    font-size: 40px;
    @include tablet { font-size: 70px; }
    @include desktop { font-size: 100px; }
  }

  &__occupation {
    overflow: hidden;
    white-space: nowrap;
    animation: type 1.5s forwards;
    font-size: $font20;
    font-weight: 600;
    margin: 20px auto 0 auto;
    @include tablet { font-size: 25px; }
    &-wrapper { display: inline-block; }
  }
  
  &__wrapper {
    background: $stockBlack;
    padding: 50px $padding5;
    margin-top: 43vh;
    @include tablet { padding: 75px $padding5; }
    @include desktop { padding: 100px 13%; }
  }

  &__subwrapper {
    text-align: center;
    @include tablet {
      @include flexCenter;
      justify-content: space-around;
    }
  }

  &__biowrapper {
    max-width: 550px;
    margin: auto;
    @include tablet { width: 50%; padding: 0 20px; margin: 0; }
    @include desktop { padding: 0; }
  }

  &__image {
    width: 100%;
    max-width: 350px;
  }

  &__bio {
    color: $stockWhite;
    font-size: $font16;
    margin: 20px 0;
  }
  
  &__resume {
    @include button;
    display: inline-block;
    &:hover {
      border-color: $stockWhite;
      background: $stockWhite;
      color: $stockBlack;
    }
  }
}
</style>