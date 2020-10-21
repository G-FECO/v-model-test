<template>
  <div>
    <InputForm />
    <hr>
    <KoreanInputForm />
    <hr>
    <CheckBox />
  </div>
</template>

<script>
import InputForm from '@/components/InputForm.vue';
import KoreanInputForm from '@/components/KoreanInputForm.vue';
import CheckBox from '@/components/CheckBox.vue';

export default {
  name: 'App',
  components: {
    InputForm,
    KoreanInputForm,
    CheckBox
  }
}
</script>