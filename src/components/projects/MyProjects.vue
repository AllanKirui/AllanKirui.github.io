<template>
  <section id="projects" class="projects fade-in" ref="projects">
    <h2 class="projects__title">
      some things I've built and
      <span class="text-alt-color">helped build</span>
    </h2>

    <div class="project__cards">
      <ProjectItem
        v-for="(project, index) in projectsData"
        :key="index"
        :title="project.title"
        :tag="project.tag"
        :description="project.description"
        :about-tags="project.about"
        :live-link="project.links.live"
        :repo-link="project.links.repo"
        :img="project.img"
        :is-collab="project.isCollab"
      />
    </div>
  </section>
</template>

<script>
import data from "@/projects-data";

import ProjectItem from "@/components/projects/ProjectItem";

export default {
  components: {
    ProjectItem,
  },
  inject: ["fadeHandler"],
  data() {
    return {
      projectsData: data,
    };
  },
  methods: {
    showFadingElement() {
      const fadingEl = this.$refs.projects;
      const fadingPoint = 150; // pixel value
      this.fadeHandler(fadingEl, fadingPoint);
    },
  },
  mounted() {
    window.addEventListener("scroll", this.showFadingElement);
  },
};
</script>

<style scoped>
.projects {
  margin-bottom: var(--m-step-2);
}

.projects__title {
  text-align: center;
}
</style>