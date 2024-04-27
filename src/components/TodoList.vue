<script>
import {defineComponent} from 'vue'

export default defineComponent({
  name: "TodoList",
  props: {
    todos: Array,
    listBools: Boolean,
  },
  methods: {

  }
})
</script>




<template>
  <div>
    <div v-auto-animate v-if="listBools">
      <h2 class="text">Добавьте хотя бы одну задачу</h2>
    </div>
    <div v-else class="todo__list">
      <ul v-auto-animate class="todo__list-items">
        <li v-for="todo in todos" class="todo__list-item">
          {{ todo }}
          <img  class="todo__list-ic" src="../assets/delete-ic.png" alt="delete">
        </li>
      </ul>
    </div>
  </div>
</template>

