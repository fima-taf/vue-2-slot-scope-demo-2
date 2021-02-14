<template>
  <Card :items="cards" subtitleSlotReturnValue="subtitle">
    <template slot="subtitle" slot-scope="props">
      <div :style="'color: ' + props.item.color">
        {{ props.item.subtitle }}
        <button @click="props.item.color = 'black'">Change color</button>
      </div>
    </template>
    <template slot="footer-extra" slot-scope="{ item }">
      {{ item.readtime }}
    </template>
  </Card>
</template>

<script>
import Card from "@/Card";
export default {
  components: {
    Card,
  },
  props: {
    items: Array,
  },
  data: () => ({
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
};
</script>

<style scoped>
</style>