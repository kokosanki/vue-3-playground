<template>
  <div class="about">
    <h1>This is an about page</h1>
    <teleport-modal />
  </div>
</template>
<script>
import TeleportModal from '../components/Teleport-Modal.vue'
export default {
  components: {
    TeleportModal
  }
}
</script>
