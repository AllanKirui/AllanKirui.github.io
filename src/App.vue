<template>
  <TheHeader />

  <div class="container">
    <main>
      <TheHero />
    </main>
  </div>
</template>

<script>
import TheHeader from "@/components/TheHeader";
import TheHero from "@/components/TheHero";

export default {
  name: "App",
  components: {
    TheHeader,
    TheHero,
  },
};
</script>
