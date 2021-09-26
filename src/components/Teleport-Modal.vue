<template>
  <h2>Look, Ma! I'm a multiroot component!</h2>
  <button @click="showModal = true">Open modal</button>
  <teleport to="body">
    <div class="teleport-modal" v-if="showModal">
      <div class="modal-message">
      <h2>I'm a modal teleported to body!</h2>
      <button @click="showModal = false">Close modal</button>
    </div>
    </div>
  </teleport>
</template>

<script>
import { ref } from '@vue/reactivity'
export default {
  setup () {
    const showModal = ref(false)

    return { showModal }
  }
}
</script>

<style>
  .teleport-modal {
    position: absolute;
    top: 0;
    height: 100vh;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: salmon;
    width: 100%;
  }
  .modal-message {
    width: 400px;
    height: 200px;
    display: flex;
    flex-direction: column;
    justify-content: center;
    align-items: center;
    background-color: antiquewhite;
    border: 2px solid salmon;
    border-radius: 5px;
    z-index: 1;
  }
</style>
