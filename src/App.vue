<template>
  <div class="container">
    <h1 class="heading">To Do List App</h1>
    <input class="input" v-model="newToDo" type="text" placeholder="what's the plan, Batman?"/>
    <button class="add-button" @click="add()">Add+</button>
    <ul class="ul" style="list-style-type: none" :key="newToDo.id">
      <li class="li" v-for="(todo, i) in todos" :key="todo.id">
        {{ i + 1 }}: {{ todo.text }}
        <button class="delete-button" @click="deleteToDo(i)">-</button>
      </li>
    </ul>
  </div>
</template>



<script>
export default {
  name: "App",

  data() {
    return {
      newToDo: "",
      todos: [
        { text: "Get Grocaries", id: 0 },
        { text: "Shopping ", id: 1 },
        { text: "Study Material", id: 2 },
      ],
    };
  },

  methods: {
    add() {
      this.todos.push({
        text: this.newToDo,
      }),
        (this.newToDo = "");
    },
    deleteToDo(i) {
      this.todos.splice(i, 1);
    },
  },
};
</script>



<style scoped>
.container {
  text-align: center;
  background-color: darkcyan;
  width: 50%;
  margin-left: 28%;
  border:1px solid black;
}

.li {
  margin-top: 8px;
  margin-bottom: 8px;
  margin-left: 30%;
  margin-right: 40%;
  border-bottom: 2px dotted white;
  padding: 0 !important;
  text-align: left !important;
}
.heading {
  font-size: 60px;
}
 .ul {
  color: black;
  font-size: 150%;
  font-weight: bold;
  font-family: sans-serif;
  padding: 0 !important;
}
.input {
  border: 3px solid rgb(25, 29, 31);
  border-radius: 12px;
  margin: o auto;
  width: 300px;
  height: 35px;
  text-indent: 45px;
}

.add-button {
  color: white;
  background-color: black;
  font-size: 15px;
  height: 30px;
  margin-left: 1%;
}
.delete-button {
  background-color: rgb(175, 76, 96);
  margin-left: 5%;
}
</style>
