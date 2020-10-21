<template>
  <div>
    <h2>v-model</h2>
    <input v-model="message" type="text">
    <p>메세지: {{ message }}</p>
  </div>
</template>

<script>
export default {
  name: 'InputForm',
  data() {
    return {
      message: ''
    }
  },
}
</script>

<style>

</style>