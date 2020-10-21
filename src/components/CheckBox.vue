<template>
  <section>
    <input type="checkbox" id="save-id" v-model="check">
    <label for="save-id">아이디 저장</label>
    <p>체크 확인: {{ check }}</p>
    <hr>
    <input type="checkbox" id="auto-login" @change="toggleChecked" :checked="autoCheck">
    <label for="auto-login">자동 로그인</label>
    <p>체크 확인: {{ autoCheck }}</p>
  </section>
</template>

<script>
export default {
  name: 'CheckBox',
  data() {
    return {
      check: false,
      autoCheck: false
    }
  },
  methods: {
    toggleChecked(e) {
      this.autoCheck = e.target.checked;
    }
  },
}
</script>