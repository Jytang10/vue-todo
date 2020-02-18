<template>
  <header>
    <input
      type="text"
      name="todoInput"
      placeholder="What to do?"
      v-model="todoValue"
    />
    <button class="submit" @click="createTodo">+</button>
  </header>
</template>

<script>
export default {
  data(){
    return {
      todoValue: ''
    }
  },
  methods: {
    createTodo(){
      this.$emit('createTodo', this.todoValue)
      this.todoValue = ''
    }
  }
};
</script>

<style lang="scss" scoped>
header {
  display: flex;

  input {
    flex: 1;
    height: 50px;
    box-sizing: border-box;
    text-indent: 15px;
    font-size: 20px;
  }

  .submit {
    width: 50px;
    height: 50px;
    font-size: 28px;
    font-weight: 700;
    line-height: 1;
    color: #171717;
    background-color: #ffce00;
    border: none;
    outline: none;
    cursor: pointer;

    &:hover {
      background-color: lighten($color: (#FFCE00), $amount: 10)
    }
    &:active {
      background-color: darken($color: (#FFCE00), $amount: 5)
    }
  }
}
</style>
