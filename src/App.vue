<template>
  <TheHeader />

  <div class="container">
    <main>
      <TheHero />
      <AboutMe />
      <MyProjects />
    </main>
  </div>
</template>

<script>
import TheHeader from "@/components/TheHeader";
import TheHero from "@/components/TheHero";
import AboutMe from "@/components/AboutMe";
import MyProjects from "@/components/MyProjects";

export default {
  name: "App",
  components: {
    TheHeader,
    TheHero,
    AboutMe,
    MyProjects,
  },
};
</script>
