<template>
    <form @submit="addTodo">
        <input
        type="text" 
        placeholder="Enter todo"
        v-model="title"
        name="title"
        />
        <button>Submit</button>
    </form>
</template>

<script>
import uuid from 'uuid'
export default {
    name : 'AddTodo',
    data() {
        return {
       title : '',
        }
    },
    methods : {
        addTodo(e){
            e.preventDefault();
            if(this.title.length > 1){
          const newTodo = {
             title : this.title,
             id : uuid.v4(),
             completed : false,
         }
         this.$emit('add-todo', newTodo),
            this.title = '';
            }
            else{
             return;
            }
        }
    }

}
</script>

<style scoped>
form {
    max-width: 100%;
    height: 100px;
    background: #f4f4f4;
    display: flex;
    flex-direction: column;
    align-items: center;
    justify-content: space-between;
}
input {
    height: 40px;
    width: 200px;
    margin: 0;
    text-align: center;
    margin-top: 20px;
    border-radius: 10px;
    border: 1px solid black;
    outline: none;
    font-size: 20px;
}
input ::placeholder{
    font-size: 40px;
}
button {
    background: rgb(12, 199, 12);
    width: 100px;
    padding: 5px 0px;
    border-radius: 10px;
    border: none;
    font-size: 1rem;
    color: white;
    outline: none;
}
</style>