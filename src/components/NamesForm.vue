<template>
  <form>
    <div>
      <label for="name">Author:</label>
      <input type="text" :value="property" @input="updateProperty($event.target.value)" />
    </div>
    <div>
      <label for="Recipient">Recipient:</label>
      <input type="text" :value="recipient" @input="updateRecipient($event.target.value)" />
    </div>
  </form>
</template>
<script>
export default {
  props: {
    property: String,
    recipient: String
  },
  setup (props, { emit }) {
    const updateProperty = (value) => {
      emit('update:property', value)
    }
    const updateRecipient = (value) => {
      emit('update:recipient', value)
    }
    return { updateProperty, updateRecipient }
  }
}
</script>
