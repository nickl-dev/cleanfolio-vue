<template>
  <div class="my-work">
    <h1 class="my-work__heading">My Work</h1>
    <Project
      v-for="(project, index) in projects"
      :key="index"
      :title="project.title"
      :description="project.description"
      :techStack="project.techStack"
      :image="project.image"
      :demo="project.demo"
      :code="project.code"
    />
  </div>
</template>

<script>
import Project from '@/components/Project.vue';
import projectScreenshot from '@/assets/project-screenshots/project-screenshot.jpg';

export default {
  name: 'MyWork',

  components: { Project },

  data() {
    return {
      /**
       * Array that stores the information for each project you want to showcase
       * Replace these placeholders with information about your projects
       */
      projects: [
        {
          title: 'Project Title',
          description: 'Project description',
          techStack: 'Tech stack used',
          image: projectScreenshot,
          demo: 'https://nickl-dev-cleanfolio.netlify.app/',
          code: 'https://nickl-dev-cleanfolio.netlify.app/'
        }
      ]
    };
  }
};
</script>

<style lang="scss">
@import '@/styles/global.scss';
.my-work {
  @include flexCenter;
  @include flexColumn;
  @include padding5;
  &__heading {
    margin-top: 150px;
  }
  @include desktop {
    margin-bottom: 30px;
  }
}
</style>
