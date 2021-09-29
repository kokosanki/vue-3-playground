<template>
  <div class="about">
    <h1>This is an about page</h1>
    <teleport-modal />
    <h2>Look, {{recipientName}}! I have {{authorProperty}}!</h2>
    <names-form v-model:property="authorProperty" v-model:recipient="recipientName" />
    <suspence-modal />
    <reactive-objects />
  </div>
</template>
<script>
import { ref } from '@vue/reactivity'
import NamesForm from '../components/NamesForm.vue'
import TeleportModal from '../components/Teleport-Modal.vue'
import SuspenceModal from '../components/SuspenceModal.vue'
import ReactiveObjects from '../components/ReactiveObjects.vue'
export default {
  components: {
    TeleportModal,
    NamesForm,
    SuspenceModal,
    ReactiveObjects
  },
  setup () {
    const authorProperty = ref('2 v-models')
    const recipientName = ref('Ma')
    return {
      authorProperty,
      recipientName
    }
  }
}
</script>
