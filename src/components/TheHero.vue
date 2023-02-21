<template>
  <section class="hero flex flex-jc-sb flex-ai-c">
    <div class="hero__text">
      <h1 class="hero__text-greeting">Hi, my name is</h1>
      <h3 class="hero__text-name">
        Allan<span class="text-alt-color">Kirui</span>.
      </h3>
      <p class="hero__text-description text-1">
        Building creative designs for the web and having fun with code are my
        favorite things to do as
        <span class="semi-bold">a self-taught developer</span>.
      </p>
      <p class="hero__text-description text-2">
        Oh, and I've been doing it all
        <span class="semi-bold">on a 12-year-computer!</span>
      </p>
    </div>

    <div class="hero__image">
      <img
        v-if="preferredTheme === 'dark'"
        src="@/assets/img/hero-dark.png"
        width="600"
        height="600"
        alt="Allan's avatar"
      />
      <img
        v-else
        src="@/assets/img/hero-light.png"
        width="600"
        height="600"
        alt="Allan's avatar"
      />
    </div>
  </section>
</template>

<script>
export default {
  props: ["theme"],
  data() {
    return {
      preferredTheme: null,
    };
  },
  watch: {
    theme(newTheme) {
      this.preferredTheme = newTheme;
    },
  },
  beforeMount() {
    this.preferredTheme = document.documentElement.getAttribute("data-theme");
  },
};
</script>

<style scoped>
.hero {
  margin-top: 123px;
  margin-bottom: var(--m-step-2);
}

.hero__text {
  max-width: 50vw;
}

.hero__text-greeting {
  margin-bottom: 2rem;
  font-size: var(--step-0);
  font-weight: normal;
}

.hero__text-name {
  margin-bottom: 1.5rem;
  font-size: var(--step-3);
  font-weight: 700;
}

.hero__text-description {
  max-width: 600px;
  font-size: var(--step-1);
  line-height: 1.5;
}

.hero__text-description.text-1 {
  margin-bottom: 2rem;
}

.hero__image img {
  max-width: 100%;
  height: 100%;
}

@media (max-width: 768px) {
  .hero {
    flex-direction: column-reverse;
    gap: 2rem;
  }

  .hero__text {
    max-width: 100%;
  }
}
</style>