<script setup>
import {ref} from 'vue'
import TodoCreator from '../components/TodoCreator.vue'
import {uid} from 'uid'

const todolist = ref([])

const createTodo = (todo) => {
  todolist.value.push({
   id:uid(),
   todo,
   isCompleted:null,
   isEditing: null
  })
}

</script>


<template>
  <main>
    <h1>Create Todo</h1>
     <TodoCreator @create-todo="createTodo()"/>
  </main>
</template>


<style lang="scss" scoped>
header {
  background-color: #f1f1f1;
  nav {
    display: flex;
    align-items: center;
    padding: 25px 16px;
    .branding {
      display: flex;
      align-items: center;
      gap: 8px;
      img {
        max-width: 50px;
      }
      h1 {
        font-size: 24px;
      }
    }
    .nav-routes {
      display: flex;
      flex: 1;
      justify-content: flex-end;
      gap: 12px;
      list-style: none;
      a {
        text-decoration: none;
        color: inherit;
      }
    }
  }
}
</style>