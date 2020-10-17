<template>
  <div>
    <input type="text" class="todo-input" placeholder="Add todo Here..." v-model="newTodo" @keyup.enter="addTodo" />

    <div v-for="(todo,index) in todos" :key="todo.id" class="todo-item">
      <div>
        {{todo.title}}
      </div>

      <div class="remove-item" @click="removeTodo(index)">&times;</div>
    </div>
    
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
      if(this.newTodo.trim().length==0){
        return;
      }

      this.todos.push({
        id: this.idForTodo,
        title: this.newTodo
      })

      this.newTodo = '';
      this.idForTodo++;
    },

    removeTodo(index){
      this.todos.splice(index,1);
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

  .todo-item{
    margin-bottom: 12px;
    display: flex;
    text-align: center;
    justify-content: space-between;
    padding-left: 150px;
    font-size: 20px;
  }

  .remove-item{
    cursor: pointer;
    margin-right: 150px;
    &:hover{
      color:black;
    }
  }
</style>
