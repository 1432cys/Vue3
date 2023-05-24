<template>
  <div>
    <h1>Generate PDF</h1>
    <div>
      <label for="text">Enter Text:</label>
      <textarea type="text" id="text" placeholder="here is textarea" v-model="textarea" />
    </div>
    <button @click="generatePDF">Generate PDF</button>
  </div>
</template>

<script>
import jsPDF from 'jspdf';

export default {
  data() {
    return {
      textInput: '',
    };
  },
  methods: {
    generatePDF() {
      const doc = new jsPDF();
      doc.text(this.textarea, 10, 10);
      doc.save('sample.pdf');
    },
  },
};
</script>

<style scoped>
h1 {
  text-align: center;
}

div {
  margin: 20px;
}

label {
  display: block;
}

input {
  width: 100%;
  padding: 5px;
  margin-top: 5px;
}

button {
  display: block;
  margin: 20px auto;
  padding: 10px 20px;
  font-size: 16px;
  cursor: pointer;
}
</style>