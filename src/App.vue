<template>
  <div class="todo">
    <div class="todo__inner">
      <h2 class="todo__title">Mutaev Todo</h2>
      <div class="todo__inp-box">
        <input v-model="inputValue" class="todo__input" type="text" placeholder="Введите название задачи">
        <button @click="addTodo" class="todo__btn">Добавить</button>
      </div>


      <div v-if="listBools">
        <h2 class="text">Добавьте хотя бы одну задачу</h2>
      </div>
      <div v-else class="todo__list">
        <ul class="todo__list-items">
          <li v-for="todo in todos" class="todo__list-item">
            {{ todo }}
            <img @click="deleteTodo(todo)" class="todo__list-ic" src="./assets/delete-ic.png" alt="">
          </li>
        </ul>
      </div>

    </div>
  </div>
</template>

<script>


export default {
  data() {
    return {
      inputValue: '',
      todos: [],
      listBool: true,
    }
  },
  methods: {
    deleteTodo(todo) {
      this.todos = this.todos.filter((t) => t !== todo)
    },
    addTodo() {
      if(this.inputValue) {
        this.todos.push(this.inputValue)
        this.inputValue = ""
      }
    },
  },
  computed: {
    listBools() {
      if (this.todos.length > 0 ) {
        return this.listBool = false
      } else {
        return this.listBool = true
      }
    }
  }
}
</script>

<style>
body {
  background-color: #c9ded1;
  font-family: "Base 05";
}
.todo {
  margin: 0 auto;
  display: flex;
  align-items: center;
  justify-content: center;


}
.todo__inner {
  width: 400px;
}
.todo__title {
  color: #286f3d;
  text-transform: uppercase;
}
.todo__input {
  border: 2px solid #286f3d;
  border-radius: 4px;
  padding: 10px;
  font-size: 16px;
  font-family: "Corbel";
  display: block;
  width: 100%;
}
.todo__input::placeholder {
  font-family: "Corbel";
}
.todo__inp-box {
  display: flex;
  gap: 5px;
}
.todo__btn {
  font-family: "Corbel";
  border: 2px solid #286f3d;
  background-color: transparent;
  text-transform: uppercase;
  font-weight: 500;
  cursor: pointer;
}
.todo__btn:hover {
  background-color: #286f3d;
  color: white;
  border: 2px solid #286f3d;
}
.todo__list-ic {
  width: 25px;
  height: 25px;
}
.todo__list-ic {
  cursor: pointer;
}
.todo__list-item {
  font-family: "Corbel";
  font-size: 19px;
  margin-bottom: 10px;
  display: flex;
  justify-content: space-between;
  gap: 5px;
}
.text {
  font-family: Corbel;
  font-weight: 400;
  color: #286f3d;
}
</style>

