<!DOCTYPE html>
<html>
<head>
  <title>Vue.js Todo List Example</title>
  <script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
</head>
<body>
  <div id="app">
    <h2>Todo List</h2>
    <input v-model="newTodo" @keyup.enter="addTodo">
    <ul>
      <li v-for="(todo, index) in todos" :key="index">
        {{ todo }}
        <button @click="removeTodo(index)">Delete</button>
      </li>
    </ul>
  </div>

  <script>
    new Vue({
      el: '#app',
      data: {
        newTodo: '',
        todos: []
      },
      methods: {
        addTodo: function() {
          if (this.newTodo !== '') {
            this.todos.push(this.newTodo);
            this.newTodo = '';
          }
        },
        removeTodo: function(index) {
          this.todos.splice(index, 1);
        }
      }
    });
  </script>
</body>
</html>