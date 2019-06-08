<template>
  <div class="content">
    <button @click="showNum = !showNum">click to change</button>
    <div class="input-group" v-if="!showNum">
      <h1>請輸入文字~~</h1>
      <h1>{{ text }}</h1>
      <input type="text" v-model="text">
    </div>
    <div class="input-group" v-else>
      <h1>請輸入數字~~</h1>
      <h1 @click="clickText()">{{ numSquare }}</h1>
      <input type="range" v-model="num" min="0" max="10">
    </div>
  </div>
</template>

<script>
export default {
  name: "Test",
  data: () => {
    return {
      text: "",
      num: 0,
      showNum: false
    };
  },
  computed: {
    numSquare() {
      return this.num ** 2;
    }
  },
  methods: {
    clickText() {
      alert("this.numSquare: " + this.numSquare);
    }
  }
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
</style>
