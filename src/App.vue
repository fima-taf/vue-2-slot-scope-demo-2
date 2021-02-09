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
    <BlogCard :items="cards" subtitleSlotReturnValue="subtitle">
      <template slot="subtitle" slot-scope="props">
        <div :style="'color: ' + props.item.color">
          {{ props.item.subtitle }}
          <button @click="props.item.color = 'black'">Change color</button>
        </div>
      </template>
      <template slot="footer-extra" slot-scope="{ item }">
        <div class="rec" v-if="item.extra">*-{{ item.extra }}-*</div>
        <br />
        {{ item.readtime }}
      </template>
    </BlogCard>
  </div>
</template>

<script>
import BlogCard from "@/components/BlogCard";

export default {
  components: {
    BlogCard,
  },
  data: () => ({
    title: "Fima's Blog",
    navTitle: "Blogy",
    navSubtitle: "(Powered by Klingon)",
    navItems: ["Login", "Updates", "About"],
    cards: [
      {
        title: "My First Blog",
        subtitle: "Some nice subtitle",
        color: "pink",
        content:
          "What is Lorem Ipsum? Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.....",
        readtime: "1 min read",
        footer: "Read More",
        extra: "Recommended",
      },
      {
        title: "My Second Blog",
        color: "green",
        subtitle: "Another nice subtitle",
        content:
          "What is Lorem Ipsum? Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronarised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum....",
        readtime: "2 min read",
        footer: "Read More",
      },
      {
        title: "My Third Blog (wow)",
        content:
          "What is Lorem Ipsum? Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining e....",
        readtime: "3 min read",
        footer: "Read More",
      },
    ],
  }),
  computed: {
    // cards() {
    //   return [
    //     {
    //       title: "My First Blog",
    //       subtitle: "Some nice subtitle",
    //       color: "pink",
    //       content:
    //         "What is Lorem Ipsum? Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining essentially unchanged. It was popularised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum.....",
    //       readtime: "1 min read",
    //       footer: "Read More",
    //     },
    //     {
    //       title: "My Second Blog",
    //       color: "green",
    //       subtitle: "Another nice subtitle",
    //       content:
    //         "What is Lorem Ipsum? Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronarised in the 1960s with the release of Letraset sheets containing Lorem Ipsum passages, and more recently with desktop publishing software like Aldus PageMaker including versions of Lorem Ipsum....",
    //       readtime: "2 min read",
    //       footer: "Read More",
    //     },
    //     {
    //       title: "My Third Blog (wow)",
    //       content:
    //         "What is Lorem Ipsum? Lorem Ipsum is simply dummy text of the printing and typesetting industry. Lorem Ipsum has been the industry's standard dummy text ever since the 1500s, when an unknown printer took a galley of type and scrambled it to make a type specimen book. It has survived not only five centuries, but also the leap into electronic typesetting, remaining e....",
    //       readtime: "3 min read",
    //       footer: "Read More",
    //     },
    //   ];
    // },
  },
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