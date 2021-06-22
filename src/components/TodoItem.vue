<template>
    <div class="todo-item" v-bind:class="{'is-completed' : todo.completed}">
       <p v-on:click="markComplete"><input type="checkbox"/> {{todo.title}}</p>
        <button @click="$emit('del-todo', todo.id)" class="del">x</button>
    </div>
</template>

<script>
export default {
    name : "TodoItem",
    props : ["todo"],
    methods : {
        markComplete() {
            this.todo.completed = !this.todo.completed;
        }
    }
}
</script>

<style scoped>
.todo-item {
background: #f4f4f4;
padding: 10px;
border-bottom: 1px #ccc dotted;
display: flex;
justify-content: space-between;
}
.is-completed {
    text-decoration: line-through;
}
.del{
    background: red;
    color: white;
    border: none;
    padding: 4px 11px;
    border-radius:  50%;
    cursor: pointer;
    font-size: 1rem;
    outline: none;
}
</style>