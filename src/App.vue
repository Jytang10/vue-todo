<template>
  <div id="app">
    <Header @createTodo="createTodo"></Header>
    <Todos :todos="todos" @removeTodo="removeTodo"></Todos>
  </div>
</template>

<script>
import Header from "@/components/Header.vue";
import Todos from "@/components/Todos.vue";
let todos = [
  {
    id: '1',
    name: 'Do homework',
    done: false
  },
  {
    id: '2',
    name: 'Walk the dog',
    done: false
  },
  {
    id: '3',
    name: 'Buy eggs',
    done: false
  },
  {
    id: '4',
    name: 'Check the mail',
    done: false
  },
  {
    id: '5',
    name: 'Go to the bank',
    done: false
  },
]
export default {
  name: "App",
  components: { Header, Todos },
  data() {
    return {
      todos
    }
  },
  methods: {
    createTodo(todo){
      let todoObject = {
        id: Math.floor(Math.random() * 1000000),
        name: todo,
        done: false
      }
      this.todos.push(todoObject)
    },
    removeTodo(id){
      this.todos = this.todos.filter(todo => todo.id !== id)
    },
  }
};
</script>

<style lang="scss">
body {
  margin: 0;
  padding: 0;
  background-color: #f3f3f3;
  font-family: Arial, Helvetica, sans-serif;
}
</style>
