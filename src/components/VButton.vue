<template>
  <button @click="onClick" class="button">ボタンだよ</button>
</template>

<script>
export default {
  methods: {
    onClick() {
      this.$emit("click");
    },
  },
};
</script>

<style scoped>
.button {
  background: teal;
  color: white;
  padding: 5px;
  border-radius: 4px;
  font-weight: bold;
  flex-shrink: 0;
  flex-grow: 0;
  box-shadow: 0px 4px 4px 0px rgba(0, 0, 0, 0.4);
}
.button:hover {
  filter: brightness(0.9);
}
.button:active {
  filter: brightness(0.8);
}
</style>
