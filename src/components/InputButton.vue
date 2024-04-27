<script lang="ts">
import {defineComponent} from 'vue'

export default defineComponent({
  name: "InputButton",
  props:{
    modelValue: String
  }
})
</script>

<template>
  <div class="todo__inp-box">
    <input
        :value="modelValue" @input="$emit('update:modelValue', $event.target.value)"
        class="todo__input"
        type="text" placeholder="Введите название задачи"
    >
    <button @click="$emit('addTodo')"  class="todo__btn">Добавить</button>
  </div>
</template>

<style scoped>

</style>

