<template>
  <section>
    <h2>input 창에서 v-model 사용</h2>
    <input v-model="message" type="text" @keyup.enter="showText">
    <p>메세지: {{ message }}</p>
    <button @click="showText">show!</button>
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
  methods: {
    showText() {
      alert(this.message);
    }
  }
}
</script>
