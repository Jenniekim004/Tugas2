<template>
  <div>
    <h1 :class="{ highlight: isHighlighted }">Elemen HTML</h1>
    <input type="text" v-model="inputText" @input="updateText">
    <p :style="{ color: textColor }">Teks yang dimasukkan: {{ inputText }}</p>
  </div>
</template>

<script>
export default {
  data() {
    return {
      isHighlighted: false,
      inputText: '',
      textColor: 'black'
    };
  },
  methods: {
    updateText(event) {
      this.inputText = event.target.value;
      if (this.inputText.length > 10) {
        this.isHighlighted = true;
      } else {
        this.isHighlighted = false;
      }
      if (this.inputText.toLowerCase() === 'merah') {
        this.textColor = 'red';
      } else if (this.inputText.toLowerCase() === 'biru') {
        this.textColor = 'blue';
      } else {
        this.textColor = 'black';
      }
    }
  }
};
</script>

<style>
.highlight {
  background-color: rgb(95, 94, 147);
}
</style>

