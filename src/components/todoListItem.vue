<template lang="pug">
  .todo-item(:class="{checked: todo.checked}")
    label.label
      .input-block
        input(
          type="checkbox"
          @change="checkTodo"
          :checked="todo.checked"
        ).input
      .title {{todo.name}}
    .button
      router-link(
        tag="button"
        :to="`./view/${todo.name}`"
      ).view ->
    .button
      button(
        type="button"
        @click="removeTodo"
      ).remove x
</template>

<script>
export default {
  props: {
    todo: Object
  },
  methods: {
    removeTodo() {
      this.$emit("removeTodo", this.todo.id);
    },
    checkTodo(e) {
      const todoItem = {
        ...this.todo,
        checked: e.target.checked
      };
      this.$emit("checkTodo", todoItem)
    },
  }
}
</script>

<style lang="scss" scoped>
  .todo-item {
    display: flex;
    align-items: center;

    &:hover {
      .remove {
        visibility: visible;
      }

      .view{
        visibility: visible;
      }
    }
  }

  .label {
    display: flex;
    align-items: center;
    flex: 1;
  }

  .input-block {
    width: 60px;
    display: flex;
    align-items: center;
    justify-content: center;
  }

  .title {
  padding: 15px 0;
  display: block;
  line-height: 1.2;
  }

  .checked .title {
    text-decoration: line-through;
  }

  .button {
    width: 40px;
  }
  
  .view {
    visibility: hidden;
    cursor: pointer;
  }

  .remove {
    background: transparent;
    border: none;
    color: firebrick;
    cursor: pointer;
    font-size: 20px;
    visibility: hidden;
  }
</style>