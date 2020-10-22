# v-model-test

<br>

- 기본적으로 `v-model`은 `input`, `textarea`, `select`와 같은 HTML 요소에 양방향 데이터 바인딩을 생성할 수 있도록 해주는 v-directive이다.
- 영어 입력, 숫자 입력을 받아서 `data` 인스턴스에 저장할 때는 큰 문제가 안 되지만 한국어, 일본어, 중국어와 같이 IME가 필요한 언어에서는 한 템포씩 느리게 데이터 바인딩이 반영되는 버그가 발생한다.
- 이러한 문제를 해결하기 위해서 `input` 이벤트를 사용해야 한다.
- `v-model`의 내부 구조를 살펴보면 `v-on`을 이용한 이벤트와 `v-bind`를 이용한 HTML 속성과의 바인딩으로 이루어져 있다. `type`이 `text`인 `input` 태그를 예시로 들어보자.
- `input` 태그는 기본적으로 `value` 속성과 `input` 이벤트를 사용한다.
- `input` 창에 텍스트 입력이 들어오면(`input` 이벤트 발생) `input` 태그의 `value` 속성에 입력한 값이 반영(`v-bind`로 `value` 속성과 연결)된다.

```vue
<template>
  <section>
    <!-- 영어, 숫자의 입력을 받는 경우 v-model만 써줘도 무방하다. -->
    <input v-model="message" type="text">
    <p>메세지: {{ message }}</p>

    <!--
      하지만 IME가 필요한 언어의 입력을 받는 경우
      v-model을 v-on('@')와 v-bind(':')로 나눠서 작성해줘야 한다.
    -->
    <input @input="korTyping" :value="korMessage" type="text">
    <p>메세지: {{ korMessage }}</p>
  </section>
</template>

<script>
export default {
  name: 'KoreanInputForm',
  data() {
    return {
      message: '',
      korMessage: '',
    }
  },
  methods: {
    korTyping(e) {
      this.korMessage = e.target.value;
    }
  }
}
</script>
```



