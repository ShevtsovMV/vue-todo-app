<template lang="pug">
  .todu-input
    input(
      v-model="todo.name"
      type="text"
      placeholder="Todo Name"
      autofocus
      @keydown.enter="addTodo"
    ).input
</template>

<script>
let uniqId = 0;
export default {
  data() {
    return {
      todo: {
        id: 0,
        name: "",
        checked: false,
      }
    };
  },
  methods: {
    addTodo() {
      this.todo.id = uniqId;
      this.$emit("addTodo", {...this.todo});
      this.todo.name = "";
      uniqId++;
    },
  },
}
</script>

<style lang="scss" scoped>
  .input {
    font-size: 24px;
    padding: 16px 16px 16px 60px;
    border: none;
    background: rgba(0, 0, 0, 0.003);
    box-shadow: inset 0 -2px 1px rgba(0, 0, 0, 0.03);
    line-height: 1.4em;
    outline: none;
    color: inherit;
    width: 100%;
    background: #fff;
  }
</style>