<template>
  <div>
    <h2>v-model = 'v-on:input' + 'v-bind:input'의 조합</h2>
    <input @input="korTyping" :value="korMessage" type="text">
    <p>메세지: {{ korMessage }}</p>
    <textarea @input="korTypingText" :value="korText" type="text" class="kor-textarea"></textarea>
    <p>메세지: {{ korText }}</p>
  </div>
</template>

<script>
export default {
  name: 'KoreanInputForm',
  data() {
    return {
      korMessage: '',
      korText: '',
    }
  },
  methods: {
    korTyping(e) {
      this.korMessage = e.target.value;
    },
    korTypingText(e) {
      this.korText = e.target.value;
    }
  }
}
</script>

<style>
.kor-textarea {
  width: 200px;
  height: 50px;
  resize: none;
}
</style>