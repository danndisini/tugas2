<template>
  <div id="app">
    <h1>Linglung!!!</h1>
    <input type="text" v-model="inputValue" @input="updateText" placeholder="Ketik Sini">
    <p :class="{ highlight: isActive }" :style="{ fontSize: fontSize + 'px', color: textColor }" class="border-paragraph">{{ outputText }}</p>
    <button @click="ngeblingbling" style="background-color: rgba(255, 255, 255, 0.5);">Highlight</button>
    <button @click="gantiwarnatext" style="background-color: rgba(255, 255, 255, 0.5);">Gnti warna</button>
    <button @click="ukurantmbh" style="background-color: rgba(255, 255, 255, 0.5);">Ukuran text (+)</button>
    <button @click="ukurankrng" style="background-color: rgba(255, 255, 255, 0.5);">Ukuran text (-)</button>
    
  </div>
</template>

<script>
export default {
  data() {
    return {
      isActive: false,
      inputValue: '',
      fontSize: 16,
      textColor: 'aqua',
    }
  },
  computed: {
    outputText() {
      return this.inputValue.toUpperCase();
    }
  },
  methods: {
    ngeblingbling() {
      this.isActive = !this.isActive;
    },
    updateText() {
      this.inputValue = this.inputValue.trim();
    },
    ukurantmbh() {
      this.fontSize += 2;
    },
    ukurankrng() {
      this.fontSize -= 2;
    },
    gantiwarnatext() {
      this.textColor = this.textColor === 'blue' ? 'red' : 'blue';
    }
  }
}
</script>

<style scoped>
.highlight {
  background-color: black;
}

h1 {
  color: #FFA500;
}

#app {
  max-width: 600px;
  margin: 20px auto;
  padding: 20px;
  border: 1px solid #ccc;
  border-radius: 5px;
  box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
  border: 2px solid rgba(0, 0, 0, 0.1);
  
}


</style>