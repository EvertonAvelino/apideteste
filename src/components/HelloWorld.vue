<template>
  <div class="hello">
    <h1>teste</h1>
    <v-btn class="mx-2" fab dark large color="purple" @click="Download()">
      Download
    </v-btn>
  </div>
</template>

<script>
import { jsPDF } from "jspdf";

export default {
  name: "HelloWorld",
  props: {
    msg: String,
  },
  methods: {
    Download() {
      const doc = new jsPDF({
        orientation: "landscape",
        unit: "in",
        format: "a4",
      });

      doc.text("teste", 1, 1);
      doc.save("teste.pdf");
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
