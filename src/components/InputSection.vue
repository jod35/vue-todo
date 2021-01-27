<template>
  <div class="input-section">
    <div class="count">
      <p>
        Task count: <strong>{{ count }}</strong>

        <span>
          Tasks complete: <strong>{{ tasksComplete.length }}</strong>
        </span>
      </p>
    </div>
    <input type="text" class="form-control" v-model="todo" />
    <input type="submit" value="Add" v-on:click="addTodo" />
     <input type="submit" value="Clear" v-on:click="deleteAll" />
    <div class="">
      <div class="todo" v-for="todo in todos" :key="todo.id">
        <p>
          <strong>{{ todo.todo }}</strong>
          <span><input type="checkbox" name="complete" id="" v-on:input="completeTask(todo.id)"/></span>
        </p>
      </div>
    </div>
  </div>
</template>
<script>
export default {
  name: "InputSection",
  components: {},
  data() {
    return {
      todo: "",
      todos: [],
      count: 0,
    };
  },
  methods: {
    addTodo() {
      this.count++;
      this.todos.unshift({
        id: this.todos.length,
        todo: this.todo,
        complete: false,
      });
      this.todo = "";
    },
    deleteAll(){
        this.todos=[];
        this.count=0;
    },
    completeTask(todoId){
        let task=this.todos.find(
            t=>t.id==todoId
        )

        task.complete= true;
    }   
  },
  computed:{
      tasksComplete(){
          return this.todos.filter(
              (t)=>t.complete==true
          )
      }
  }
};
</script>
<style>
.input-section {
  width: 60%;
  margin: auto;
}
</style>