<template>
  <nav class="nav">
    <router-link
      class="nav__link"
      active-class="nav__link--active"
      exact
      to="/"
    >
      <PersonIcon 
        title="About Me" 
        :size="iconSize" 
        @click="scrollToTop" 
      />
    </router-link>

    <router-link
      class="nav__link"
      active-class="nav__link--active"
      to="/my-work"
    >
      <CodeIcon 
        title="My Work" 
        :size="iconSize" 
        @click="scrollToTop" 
      />
    </router-link>

    <router-link
      class="nav__link"
      active-class="nav__link--active"
      to="/contact"
    >
      <MailIcon 
        title="Contact Me" 
        :size="iconSize" 
      />
    </router-link>
  </nav>
</template>

<script>
import PersonIcon from "vue-material-design-icons/Account.vue"
import CodeIcon from "vue-material-design-icons/Xml.vue"
import MailIcon from "vue-material-design-icons/Email.vue"

export default {
  name: "Nav",

  components: {
    PersonIcon,
    CodeIcon,
    MailIcon
  },

  data() {
    return {
      iconSize: 35,
    }
  },

  methods: {
    scrollToTop() {
      window.scrollTo({ top: 0, behavior: "smooth" })
    }
  }
}
</script>

<style lang="scss">
@import "@/styles/global.scss";

.nav {
  @include flexCenter;
  height: 60px;
  box-shadow: 0 3px 3px -2px rgba($stockBlack, 0.3);
  position: fixed;
  top: 0;
  width: 100%;
  background: white;
  
  &__link {
    @include iconLink;
    margin: 0 20px;
    transition: $transition;
    &:hover { box-shadow: 0 3px 2px -2px rgba($stockBlack, 1); }
    &--active { box-shadow: 0 3px 2px -2px rgba($stockBlack, 0.5); }
  }
}
</style>