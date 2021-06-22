<template>
  <div id="app">
    <Header />
    <AddTodo v-on:add-todo="addTodoo"/>
    <Todos  v-bind:todos="todos" v-on:del-todo="deleteTodo"/>
    <DeleteTodo v-on:clearTodos="clearTodos"/>
  </div>
</template>

<script>
import Todos from './components/Todos.vue'
import Header from './components/Layout/Header.vue'
import AddTodo from './components/Layout/Form.vue'
import DeleteTodo from './components/Layout/DeleteTodo.vue'
export default {
  name: 'App',
  components: {
    Todos,
    Header,
    AddTodo,
    DeleteTodo
  },
  data() {
    return {
     todos : [
       {
         id : 1,
         title : 'Codeee',
         completed : false,
       },
        {
         id : 2,
         title : 'Sleep',
         completed : false,
       },
        {
         id : 3,
         title : 'Go to the gym',
         completed : false,
       }
     ]
     }
    },
    methods : {
    deleteTodo(id) {
      this.todos = this.todos.filter(todo => todo.id !== id);
    },
    addTodoo(newTodo){
      this.todos = [...this.todos, newTodo]
    },
    clearTodos(){
     !completed ? this.todos.splice(0) : null;
    }
    }
}
</script>

<style>
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
  }
  body {
    font-family: Arial, Helvetica, sans-serif;
    line-height: 1.4;
    }
</style>
