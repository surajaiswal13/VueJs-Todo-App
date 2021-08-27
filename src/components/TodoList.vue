<template>
  <div class="container">
    <div class="row">
      <div class="col-12">
        <p class="display-3">Vue TODO app</p>
      </div>
    </div>
    <div class="row">
      <NewTodo @on-addtodo="addTodo($event)" />
    </div>
    <div class="row">
      <div class="col-12 col-lg-6">
        <ul class="list-group">
          <!-- Iterating through data -->
          <!-- KEY makes sure we are not iterting over the same object over and over again -->
          <!-- <li v-for="(todo , index) in todos" :key="index">{{ todo.todoString }}</li> -->
          <Todo
            v-for="(todo, index) in todos"
            :key="index"
            :todoString="todo.todoString"
            :completed="todo.completed"
            @on-delete="deleteTodo(todo)"
            @on-toggle="toggleTodo(todo)"
            @on-edit="editTodo(todo, $event)"
          />
        </ul>
      </div>
    </div>
  </div>
</template>

<script>
import Todo from "./Todo.vue";
import NewTodo from "./newTodo.vue"

export default {
  //   name: "TodoList",

  components: {
    Todo,
    NewTodo
  },

  data() {
    return {
      todos: [
        { todoString: "Make Angular course", completed: false },
        { todoString: "Cook some food", completed: true },
        { todoString: "Make Youtube Videos", completed: true },
        { todoString: "Publish these videos", completed: false },
      ],
    };
  },

  // Brain
//   method: {
//     addTodo(newTodo) {
//       // this.todos.push() = newTodo
//       this.todos.push({
//         todoString: newTodo,
//         Completed: false,
//       });
//     },
//     toggleTodo(todo) {
//       todo.Completed = !todo.Completed;
//     },
//     editTodo(todo, newTodoString) {
//       todo.todoString = newTodoString;
//     },
//     deleteTodo(deleteTodo) {
//       this.todos = this.todos.filter((todo) => todo !== deleteTodo);
//       // this.todos = this.todos.filter(todos => todos.todoString !== deleteTodo.todoString);
//     },
//   },

  methods: {
    addTodo(newTodo) {
      this.todos.push({
        todoString: newTodo,
        completed: false
      });
    },
    toggleTodo(todo) {
      todo.completed = !todo.completed;
    },
    editTodo(todo, newTodoString) {
      todo.todoString = newTodoString;
    },
    deleteTodo(deleteTodo) {
      this.todos = this.todos.filter(todo => todo !== deleteTodo);
    }
  }

  // props:{
  //     newmsg:String,
  //     // msh:String
  // }
};
</script>

<style>
</style>