<template>
  <section class="hero flex flex-jc-sb flex-ai-c">
    <div class="hero__text">
      <p class="hero__text-greeting">Hi, my name is</p>
      <p class="hero__text-name">Allan<span class="gray">Kirui</span>.</p>
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
        src="@/assets/img/hero-light.png"
        width="600"
        height="600"
        alt="Allan's avatar"
      />
    </div>
  </section>
</template>

<style scoped>
.hero {
  margin-bottom: var(--m-step-2);
}

.hero__text {
  max-width: 50vw;
}

.hero__text-greeting {
  margin-bottom: 2rem;
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