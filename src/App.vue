<template>
  <TheHeader />

  <div class="container">
    <main>
      <TheHero />
      <AboutMe />
    </main>
  </div>
</template>

<script>
import TheHeader from "@/components/TheHeader";
import TheHero from "@/components/TheHero";
import AboutMe from "@/components/AboutMe";

export default {
  name: "App",
  components: {
    TheHeader,
    TheHero,
    AboutMe,
  },
};
</script>
