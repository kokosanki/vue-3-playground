<template>
  <teleport to="#app">
    <h2>Look, Ma! I'm suspence modal!</h2>
    <button @click="showModal = true">Open modal</button>
    <div class="teleport-modal" v-if="showModal">
      <div class="modal-message">
      <Suspense>
        <template #default>
          <dnd-data />
        </template>
        <template #fallback>Loading...</template>
      </Suspense>
      <button @click="showModal = false">Close modal</button>
      </div>
    </div>
  </teleport>
</template>

<script>
import { ref } from '@vue/reactivity'
import DndData from './DndData.vue'
import { watch } from '@vue/runtime-core'
export default {
  components: {
    DndData
  },
  setup (props) {
    const showModal = ref(false)

    watch(showModal, () => {
      // The use of .value with ref
      console.log('ShowModal: ', showModal)
      console.log('ShowModal value: ', showModal.value)
    })

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
