<template>
    <div>
        <button @click="$emit('clearTodos', )">Clear</button>
    </div>
</template>

<script>
export default {
    name : 'DeleteTodo'
}
</script>
<style scoped>
   button {
       width : 100px;
       background : black;
       color: white;
       border-radius: 10px;
       margin: 0 auto;
       padding: 10px;
       font-size: 0.9rem;
       display: block;
       margin-top: 10px;
       border: none;
       outline: none;
       cursor: pointer;
   }
</style>