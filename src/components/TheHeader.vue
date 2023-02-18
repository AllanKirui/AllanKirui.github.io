<template>
  <header class="header">
    <nav class="nav flex flex-jc-sb flex-ai-c">
      <a href="/" class="header__logo"
        >a<span class="text-alt-color">k</span></a
      >

      <label class="header__toggler" aria-label="Switch theme">
        <input
          ref="check"
          type="checkbox"
          @change="$emit('change-theme', this.$refs.check)"
        />
        <span class="toggle"></span>
      </label>

      <div class="header__links">
        <a href="#about">about</a>
        <a href="#projects">projects</a>
        <a href="#contact">contact</a>
      </div>
    </nav>
  </header>
</template>

<script>
export default {
  methods: {
    preCheckDarkToggle() {
      if (document.documentElement.getAttribute("data-theme") === "dark") {
        this.$refs.check.checked = true;
      }
    },
  },
  mounted() {
    this.preCheckDarkToggle();
  },
};
</script>

<style scoped>
.header {
  width: 100%;
  margin-bottom: 2.5rem;
}

.nav {
  padding: var(--p-step-0) var(--p-step-1);
  margin: 0 auto;
  max-width: 86.25rem;
  position: relative;
}

.header__logo {
  font-size: 2rem;
  font-weight: 700;
}

.header__toggler {
  position: absolute;
  top: 50%;
  left: 50%;
  transform: translate(-50%, -50%);
}

.header__toggler input[type="checkbox"] {
  visibility: none;
  display: none;
}

.header__toggler .toggle {
  position: relative;
  display: block;
  width: 3.125rem;
  height: 1.5rem;
  background-color: hsl(210, 3%, 75%);
  border-radius: 50px;
  cursor: pointer;
  overflow: hidden;
  transition: ease-in;
}

.header__toggler input[type="checkbox"]:checked ~ .toggle {
  background-color: hsl(13, 50%, 69%);
}

.header__toggler .toggle::before,
.header__toggler .toggle::after {
  content: "";
  position: absolute;
  top: 3px;
  width: 1.125rem;
  height: 1.125rem;
  border-radius: 50%;
  transition: 0.5s;
}

.header__toggler .toggle::before {
  left: 3px;
  background-color: hsl(0, 0%, 100%);
}

.header__toggler input[type="checkbox"]:checked ~ .toggle::before {
  transform: translateX(-50px);
}

.header__toggler .toggle::after {
  right: 3px;
  background: hsl(211, 66%, 7%);
  transform: translateX(50px);
}

.header__toggler input[type="checkbox"]:checked ~ .toggle::after {
  transform: translateX(0);
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
  background: var(--nav-link-underline-color);
  border-radius: 50px;
  opacity: 0;
  transition: opacity var(--transition-300);
}

.header__links a:hover {
  color: var(--nav-link-color);
}

.header__links a:hover::before {
  opacity: 1;
}

@media (max-width: 768px) {
  .header__toggler .toggle {
    width: 2.5rem;
    height: 20px;
  }

  .header__toggler .toggle::before,
  .header__toggler .toggle::after {
    top: 2px;
    width: 1rem;
    height: 1rem;
  }

  .header__toggler .toggle::before {
    left: 2px;
  }

  .header__toggler .toggle::after {
    right: 2px;
  }
}
</style>