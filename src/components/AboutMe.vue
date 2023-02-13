<template>
  <section id="about" class="about">
    <div class="about__images"></div>

    <div class="about__text">
      <h2 class="about__text-title">about <span class="gray">me</span></h2>
      <p class="about__text-description text-1">
        My name is <span class="semi-bold">Allan</span>, and I'm
        <span class="semi-bold">from Kenya</span>. I've been learning how to
        code for a while now and have a grown a passion for front-end web
        development.
      </p>
      <p class="about__text-description text-2">
        These are some of the skills I learned along the way in my journey:
      </p>
      <div class="skills-wrapper flex flex-jc-c">
        <ul class="about__text-skills skills-1">
          <li>HTML</li>
          <li>CSS</li>
          <li>JavaScript</li>
        </ul>
        <ul class="about__text-skills skills-2">
          <li>SASS</li>
          <li>Vue</li>
          <li>SQL Basics</li>
        </ul>
        <ul class="about__text-skills skills-3">
          <li>Git</li>
          <li>GitHub</li>
          <li>Responsive Design</li>
        </ul>
      </div>
      <p class="about__text-description text-3">
        I am currently diving deeper into the VueJS ecosystem whilst learning
        how to interact with databases using SQL and the importance of data
        structures and algorithms through JavaScript.
      </p>
    </div>
  </section>
</template>

<style scoped>
.about {
  margin-bottom: var(--m-step-2);
  text-align: center;
  position: relative;
}

.about__images {
  position: absolute;
  width: 100%;
  height: 100%;
  background-image: url("@/assets/img/logo-js.svg"),
    url("@/assets/img/logo-vue.svg"), url("@/assets/img/logo-sass.svg"),
    url("@/assets/img/logo-inkscape.svg"), url("@/assets/img/logo-db.svg"),
    url("@/assets/img/logo-data.svg"), url("@/assets/img/logo-git.svg"),
    url("@/assets/img/logo-github.svg");
  background-repeat: no-repeat;
  background-size: 60px;
  background-position: 8% 30px, 92% 33px, left 45%, right 45%, 8% 80%, 92% 80%,
    35% bottom, 65% bottom;
  z-index: 1;
}

.about__text {
  max-width: 700px;
  margin: 0 auto;
  padding-bottom: 8rem;
  position: relative;
  z-index: 2;
}

.about__text-description {
  line-height: 1.5;
}

.about__text-description.text-1 {
  margin-bottom: var(--m-step--1);
}

.about__text-description.text-2 {
  margin-bottom: 1.5rem;
}

.skills-wrapper {
  gap: 3.125rem;
  margin-bottom: var(--m-step--1);
  text-align: left;
}

.about__text-skills li {
  position: relative;
  font-weight: 600;
}

.about__text-skills li::before {
  content: "▹";
  position: absolute;
  top: 50%;
  left: -1.375rem;
  transform: translateY(-50%);
  color: var(--color-pearl-dark-grey);
  font-size: var(--step-0);
  line-height: 12px;
}

@media (max-width: 960px) {
  .about__images {
    display: none;
  }

  .about__text {
    padding-bottom: 0;
  }
}

@media (max-width: 768px) {
  .about__text-description {
    text-align: left;
  }

  .skills-wrapper {
    justify-content: left;
    margin-left: 2rem;
  }
}

@media (max-width: 480px) {
  .skills-wrapper {
    flex-direction: column;
    gap: 0;
  }
}
</style>