<template>
  <div>
      <h1>TO-DO</h1>
    <div>
      <input id="todo" type="text" v-model="todoItem" placeholder="Enter Task"/>
      <button :disabled="!todoItem" @click="add()">Add</button>
      <button @click="removeSelected()">Remove</button>
    </div>
    <div class="todos" v-if="todos && todos.length > 0">
      <ul>
        <li><input type="checkbox" id="selectAll" @change="selectAll()" v-model="select"><label for="selectAll">Select All</label></li>
        <li v-for="(todo, i) in todos" :key="i">
          <input type="checkbox" :id="todo" :value="todo" v-model="checked" />
          <label :for="todo">{{ todo.toUpperCase() }}</label>

        </li>
      </ul>
    </div>
    
  </div>
</template>

<script>
export default {
  data: () => {
    return {
      select: false,
      todoItem: "",
      todos: [],
      checked: []
    };
  },
  methods: {
    add() {
      this.todos.push(this.todoItem);
      this.todoItem = "";
    },
    removeSelected() {
      for (let i of this.checked) {
        this.todos = this.todos.filter(todo => {
          return i !== todo;
        });
      }
      this.select = false;
    },
    selectAll() {
      if (this.select) {
        this.checked = [];
        for (let i of this.todos) {
          this.checked.push(i);
        }
      } else {
        this.checked = [];
      }
    }
  }
};
</script>
<style>
</style>