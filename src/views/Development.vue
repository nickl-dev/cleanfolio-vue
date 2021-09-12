<template>
  <div class="development">
    <h1 class="development__heading">DEVELOPMENT</h1>

    <!-- Looping through your projects -->
    <Project
      v-for="project in projects"
      v-bind:key="project.index"
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
// Project component that will display each project in the projects array
import Project from "@/components/Project.vue";
import projectScreenshot from "@/assets/project-screenshots/project-screenshot.jpg";

export default {
  // Name
  name: "Development",

  // Components
  components: {
    Project,
  },

  // Data
  data: () => {
    return {
      // Array that stores the information for each project you want to showcase
      // Replace these placeholders with information about your projects
      projects: [
        {
          title: "Project Title",
          description: "Project description",
          techStack: "Tech stack that you used",
          image: projectScreenshot,
          demo: "https://cleanfolio.netlify.app/",
          code: "https://cleanfolio.netlify.app/"
        },
        {
          title: "Project Title",
          description: "Project description",
          techStack: "Tech stack that you used",
          image: projectScreenshot,
          demo: "https://cleanfolio.netlify.app/",
          code: "https://cleanfolio.netlify.app/"
        },
        {
          title: "Project Title",
          description: "Project description",
          techStack: "Tech stack that you used",
          image: projectScreenshot,
          demo: "https://cleanfolio.netlify.app/",
          code: "https://cleanfolio.netlify.app/"
        }
      ],
    };
  },
};
</script>

<style lang="scss">
@import "@/styles/global.scss";

.development {
  @include flexCenter;
  @include flexColumn;
  @include padding5;

  &__heading {
    margin-top: 10vh;

    @include desktop {
      margin: 10vh 0;
    }
  }
}
</style>
