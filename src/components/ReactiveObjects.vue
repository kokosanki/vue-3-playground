<template>
    <h2>Look, Ma! I'm a reactive example!</h2>
    <div>{{exampleText.title}}</div>
    <button @click="changeMessage">Change message</button>
</template>

<script>
import { reactive } from '@vue/reactivity'
export default {
  setup (props) {
    const exampleText = reactive({
      title: 'Hello, Vue 3'
    })

    const changeMessage = () => {
      exampleText.title === 'Hello, Vue 3'
        ? exampleText.title = 'Wchodzi kogut do łazienki, a tam zakręcone kurki'
        : exampleText.title = 'Hello, Vue 3'
    }
    return { exampleText, changeMessage }
  }
}
</script>

<style>

</style>
