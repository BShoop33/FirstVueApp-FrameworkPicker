<template>
  <div id="app">
    <h1 class="header">Hello Frontend Devs</h1>
    <p class="promptQuestion">What is your favorite JS framework?</p>
    <button class="AngularButton" @click="angularSelected">Angular</button>
    <button class="VueButton" @click="vueSelected">Vue</button>
    <button class="ReactButton" @click="reactSelected">React</button>
    <div v-if="selection === 'Angular'">
      <p class="selectionMessage">
        "Good choice! <strong>Angular</strong> is a great tool!"
      </p>
      <img
        class="Logo"
        src="https://www.stickyminds.com/sites/default/files/article/2017/angular-js.png"
        alt="Angular Logo"
      />
    </div>
    <div v-else-if="selection === 'Vue'">
      <p class="selectionMessage">
        "Good choice! <strong>Vue</strong> is a great tool!
      </p>
      <img
        class="Logo"
        src="https://cdn-images.threadless.com/threadless-media/artist_shops/shops/vue/products/195796/shirt-1490420513-abd7b25b157f3450ce8c2a09ee51c36e.png?v=3&d=eyJvbmx5X21ldGEiOiBmYWxzZSwgImZvcmNlIjogZmFsc2UsICJvcHMiOiBbWyJ0cmltIiwgW2ZhbHNlLCBmYWxzZV0sIHt9XSwgWyJyZXNpemUiLCBbXSwgeyJ3aWR0aCI6IDk5Ni4wLCAiYWxsb3dfdXAiOiBmYWxzZSwgImhlaWdodCI6IDk5Ni4wfV0sIFsiY2FudmFzX2NlbnRlcmVkIiwgWzEyMDAsIDEyMDBdLCB7ImJhY2tncm91bmQiOiAiZmZmZmZmIn1dLCBbInJlc2l6ZSIsIFs4MDBdLCB7fV0sIFsiY2FudmFzX2NlbnRlcmVkIiwgWzgwMCwgODAwLCAiI2ZmZmZmZiJdLCB7fV0sIFsiZW5jb2RlIiwgWyJqcGciLCA4NV0sIHt9XV19"
        alt="Vue Logo"
      />
    </div>
    <div v-else-if="selection === 'React'">
      <p class="selectionMessage">
        "Good choice! <strong>React</strong> is a great tool!
      </p>
      <img
        class="Logo"
        src="https://c.wallhere.com/photos/02/95/reactJS_Facebook_JavaScript_minimalism_artwork_simple_background-11095.png!d"
        alt="React Logo"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selection: "",
      imageSrc: "",
    };
  },
  methods: {
    angularSelected() {
      this.selection = "Angular";
    },
    vueSelected() {
      this.selection = "Vue";
    },
    reactSelected() {
      this.selection = "React";
    },
  },
};
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.header {
  color: black;
  font-family: "Times New Roman";
}

.Logo {
  max-height: 20em;
  max-width: 40em;
}

.promptQuestion {
  color: black;
  font-family: "Times New Roman";
  font-size: 16pt;
  font-weight: 600;
}

.selectionMessage {
  color: black;
}
</style>