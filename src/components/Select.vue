<template>
  <section>
    <h2>select 태그에서 v-model 사용</h2>
    <select name="fruit" v-model="selectedFruit">
      <option value="apple">apple</option>
      <option value="kiwi">kiwi</option>
    </select>
    <p>선택한 과일: {{ selectedFruit }}</p>
    <hr>
    <select name="user" @change="pickedUser" :value="selectedUser">
      <option value="user1">user1</option>
      <option value="user2">user2</option>
    </select>
    <p>선택한 유저: {{ selectedUser }}</p>
  </section>
</template>

<script>
export default {
  data() {
    return {
      selectedFruit: 'No Select',
      selectedUser: 'No Select!'
    }
  },
  methods: {
    pickedUser(e) {
      this.selectedUser = e.target.value;
    }
  }
}
</script>
