<template>
  <div>
    <input type="text" class="todo-input" placeholder="Add todo Here..." v-model="newTodo" @keyup.enter="addTodo" />

    <div v-for="todo in todos" :key="todo.id" class="todo-item">{{todo.title}}</div>
  </div>
</template>

<script>
export default {
  name: "Todolist",
  data(){
    return{
      newTodo: '',
      idForTodo: 1,
      todos:[],
    }
  },
  methods:{
    addTodo(){
      if(this.newTodo.trim()==0){
        return;
      }

      this.todos.push({
        id: this.idForTodo,
        title: this.newTodo
      })

      this.newTodo = '';
      this.idForTodo++;
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  .todo-input{
    width: 50%;
    padding: 10px 18px;
    font-size: 18px;
    margin-bottom: 10px;
  }

  &:focus{
    outline: 0;
  }
</style>
