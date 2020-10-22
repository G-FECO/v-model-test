<template>
  <section>
    <h2>input 창에서 v-model 사용</h2>
    <input v-model="message" type="text">
    <p>메세지: {{ message }}</p>
  </section>
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
