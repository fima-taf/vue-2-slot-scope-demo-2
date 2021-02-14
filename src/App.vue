<template>
  <div id="base">
    <nav>
      <div class="left">
        <div class="nav-title">
          {{ navTitle }} <span class="nav-subtitle">{{ navSubtitle }}</span>
        </div>
      </div>
      <div class="right">
        <template v-for="(item, index) in navItems">
          <a href="#" :key="index">{{ item }}</a>
        </template>
      </div>
    </nav>
    <h1>{{ title }}</h1>
    <blog-cards :items="cards" />
  </div>
</template>

<script>
import BlogCards from "@/BlogCards";

export default {
  components: {
    BlogCards,
  },
  data: () => ({
    title: "Fima's Blog",
    navTitle: "Blogy",
    navSubtitle: "(Powered by Klingon)",
    navItems: ["Login", "Updates", "About"],
  }),
};
</script>

<style lang="scss">
#base {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  text-align: center;
  font-size: 24px;
  color: #424242;

  nav {
    display: flex;
    justify-content: space-between;
    background-color: #B2DFDB;
    padding: 2%;

    .nav-title {
      font-size: 1.1em;
    }

    .nav-subtitle {
      font-size: 0.7em;
    }

    a {
      margin: 0 6px;
      color: #00695C;
    }
  }

  h1 {
    font-size: 3em;
  }

  .rec {
    font-size: 0.5em;
  }
}
</style>