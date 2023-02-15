<template>
  <header class="header">
    <nav class="nav flex flex-jc-sb flex-ai-c">
      <a href="/" class="header__logo"
        >a<span class="text-alt-color">k</span></a
      >

      <div class="header__links">
        <a href="#about">about</a>
        <a href="#projects">projects</a>
        <a href="#contact">contact</a>
      </div>
    </nav>
  </header>
</template>

<style scoped>
.header {
  width: 100%;
  margin-bottom: 2.5rem;
}

.nav {
  padding: var(--p-step-0) var(--p-step-1);
  margin: 0 auto;
  max-width: 86.25rem;
}

.header__logo {
  font-size: 2rem;
  font-weight: 700;
}

.header__links a {
  position: relative;
  font-size: var(--step-1);
  font-weight: 500;
  transition: color var(--transition-300);
}

.header__links a:not(:last-child) {
  margin-right: 2.5rem;
}

.header__links a::before {
  content: "";
  display: block;
  position: absolute;
  height: 3px;
  left: 0;
  right: 0;
  bottom: -24px;
  background: linear-gradient(
    to right,
    var(--color-gray),
    var(--color-pearl-dark-grey)
  );
  opacity: 0;
  transition: opacity var(--transition-300);
}

.header__links a:hover {
  color: var(--color-pearl-dark-grey);
}

.header__links a:hover::before {
  opacity: 1;
}
</style>