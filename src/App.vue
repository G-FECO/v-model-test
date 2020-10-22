<template>
  <div>
    <InputForm />
    <KoreanInputForm />
    <CheckBox />
    <Select />
    <hr>
    <b>v-model 참고 문서</b>
    <ul @click="goUrl">
      <li>https://joshua1988.github.io/web-development/vuejs/v-model-usage/</li>
      <li>https://mber.tistory.com/60</li>
    </ul>
  </div>
</template>

<script>
import InputForm from '@/components/InputForm.vue';
import KoreanInputForm from '@/components/KoreanInputForm.vue';
import CheckBox from '@/components/CheckBox.vue';
import Select from '@/components/Select.vue';

export default {
  name: 'App',
  components: {
    InputForm,
    KoreanInputForm,
    CheckBox,
    Select
  },
  methods: {
    goUrl(e) {
      window.open(e.target.innerText);
    }
  }
}
</script>

<style>
h2 {
  margin: 0 0 10px 0;
}

section {
  width: 700px;
  border: 1px solid silver;
  padding: 10px;
  margin-bottom: 20px;
}

ul {
  padding: 0;
}

ul > li {
  list-style: none;
  color: #00f;
  padding: 5px;
}

ul > li:hover {
  cursor: pointer;
  text-decoration: underline;
}
</style>
