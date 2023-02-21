<template>
  <TheHeader @change-theme="switchTheme" />

  <div class="container">
    <main>
      <TheHero :theme="theme" />
      <AboutMe />
      <MyProjects />
      <ContactMe />
    </main>
  </div>

  <TheFooter />
</template>

<script>
import TheHeader from "@/components/nav/TheHeader";
import TheHero from "@/components/hero/TheHero";
import AboutMe from "@/components/about/AboutMe";
import MyProjects from "@/components/projects/MyProjects";
import ContactMe from "@/components/contact/ContactMe";
import TheFooter from "@/components/footer/TheFooter";

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
  data() {
    return {
      theme: null,
    };
  },
  methods: {
    switchTheme(el) {
      const themeToggler = el;
      const isChecked = themeToggler.checked;

      if (!isChecked) {
        localStorage.setItem("theme", "light");
        document.documentElement.setAttribute("data-theme", "light");
        themeToggler.checked = false;
        this.theme = "light";
      } else {
        localStorage.setItem("theme", "dark");
        document.documentElement.setAttribute("data-theme", "dark");
        themeToggler.checked = true;
        this.theme = "dark";
      }
    },
    detectColorScheme() {
      let theme = "light";

      // localStorage can be used to override OS theme settings
      if (localStorage.getItem("theme")) {
        if (localStorage.getItem("theme") === "dark") {
          theme = "dark";
        }
      } else if (!window.matchMedia) {
        // check if the matchMedia() method is supported
        return false;
      } else if (window.matchMedia("(prefers-color-scheme: dark)").matches) {
        // if the OS theme setting matches 'dark'
        theme = "dark";
      }

      // if dark theme is preferred, update the document with the 'dark-theme' attribute
      if (theme === "dark") {
        document.documentElement.setAttribute("data-theme", "dark");
      } else if (theme === "light") {
        document.documentElement.setAttribute("data-theme", "light");
      }
    },
  },
  created() {
    // check if the user has set a theme preference
    this.detectColorScheme();
  },
};
</script>
