<template>
  <div class="about">
    <h1>This is an about page</h1>
    <teleport-modal />
    <h2>Look {{recipientName}}! I have {{authorProperty}}!</h2>
    <names-form v-model:property="authorProperty" v-model:recipient="recipientName" />
  </div>
</template>
<script>
import { ref } from '@vue/reactivity'
import NamesForm from '../components/NamesForm.vue'
import TeleportModal from '../components/Teleport-Modal.vue'
export default {
  components: {
    TeleportModal,
    NamesForm
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
