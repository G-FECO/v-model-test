<template>
  <section>
    <h2>input, textarea에 한글 입력 시 v-model 구현 방법</h2>
    <input @input="korTyping" :value="korMessage" type="text">
    <p>메세지: {{ korMessage }}</p>
    <!-- input, textarea 태그 v-model = 'v-on:input' + 'v-bind:value'의 조합 -->
    <textarea @input="korTypingText" :value="korText" type="text" class="kor-textarea"></textarea>
    <p>메세지: {{ korText }}</p>
    <button @click="showText">show!</button>
  </section>
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
    },
    showText() {
      alert(this.korMessage);
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
