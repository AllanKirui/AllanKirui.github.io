<template>
  <TheHeader />

  <div class="container">
    <main>
      <TheHero />
      <AboutMe />
      <MyProjects />
      <ContactMe />
    </main>
  </div>

  <TheFooter />
</template>

<script>
import TheHeader from "@/components/TheHeader";
import TheHero from "@/components/TheHero";
import AboutMe from "@/components/AboutMe";
import MyProjects from "@/components/MyProjects";
import ContactMe from "@/components/ContactMe";
import TheFooter from "@/components/TheFooter";

export default {
  name: "App",
  components: {
    TheHeader,
    TheHero,
    AboutMe,
    MyProjects,
    ContactMe,
    TheFooter,
  },
};
</script>
