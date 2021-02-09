<template>
  <div>
    <div class="blog-card" v-for="(item, index) in items" :key="index">
      <div class="header">
        <div>{{ item.title }}</div>
        <div class="subtitle">
          <slot name="subtitle" :item="item"></slot>
        </div>
      </div>
      <div class="body">
        {{ item.content }}
      </div>
      <div class="footer">
        <button>{{ item.footer }}</button>
        <slot name="footer-extra" :item="item"></slot>
      </div>
    </div>
  </div>
</template>

<script>
export default {
  props: {
    items: Array,
    subtitleSlotReturnValue: String,
  },
};
</script>

<style lang="scss" scoped>
.blog-card {
  margin: 50px;
  border: 1px solid #BDBDBD;
  border-radius: 50px;
  padding: 10px;

  &:hover {
    box-shadow: 0 0 2.2px rgba(0, 0, 0, 0.034), 0 0 5.3px rgba(0, 0, 0, 0.048),
      0 0 10px rgba(0, 0, 0, 0.06), 0 0 17.9px rgba(0, 0, 0, 0.072),
      0 0 32px rgba(0, 0, 0, 0.1);
    transition: box-shadow 100ms;
  }

  .header {
    padding: 4%;
    font-size: 2em;

    .subtitle {
      font-size: 0.5em;
      max-height: 10vh;
      overflow-y: auto;
    }
  }

  .body {
    padding: 4%;
    font-size: 0.8em;
  }

  .footer {
    display: flex;
    justify-content: space-between;
    padding: 4%;
    font-size: 1.2em;

    button {
      border: 1px solid #00796B;
      color: #00796B;
      border-radius: 3px;
      background-color: transparent;
      font: inherit;
      font-size: 0.7em;

      &:focus {
        outline: none;
      }

      &:active {
        background-color: #EEEEEE;
        transition: background-color 100ms;
      }
    }
  }
}
</style>