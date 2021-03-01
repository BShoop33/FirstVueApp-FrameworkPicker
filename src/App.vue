<template>
  <div id="app">
    <h1 class="header">Hello Frontend Devs</h1>
    <p class="promptQuestion">What is your favorite JS framework?</p>
    <button class="AngularButton" @click="angularSelected">Angular</button>
    <button class="VueButton" @click="vueSelected">Vue</button>
    <button class="ReactButton" @click="reactSelected">React</button>
    <!-- Evaluates whether the state of selection equals 'Angular', 'Vue', or 'React'. Those states are set by the user clicking
    the button associated with those three options. If the state equals one of those three, then code within this div renders. If
    the selection variable does not match any of those three states, then the code within this div does not render.    
     -->
    <div
      v-if="
        selection === 'Angular' || selection === 'Vue' || selection === 'React'
      "
    >
      <!-- When rendered, displays the selection message with the current selection variable state inserted -->
      <p class="selectionMessage">
        "Good choice! <strong>{{ selection }}</strong> is a great tool!"
      </p>
      <!-- When rendered, evaluates whether the selection variable state matches 'Angular', 'Vue', or 'React'. If selection matches
      one of those three states, the image associated with that state renders. If selection does not match any of those three states (a
      condition that should not occur because this entire div should not render if that occurs), then a default 'no-image' picture will render. 
      -->
      <img
        class="Logo"
        :src="
          selection === 'Angular'
            ? 'https://www.stickyminds.com/sites/default/files/article/2017/angular-js.png'
            : selection === 'Vue'
            ? 'https://cdn-images.threadless.com/threadless-media/artist_shops/shops/vue/products/195796/shirt-1490420513-abd7b25b157f3450ce8c2a09ee51c36e.png?v=3&d=eyJvbmx5X21ldGEiOiBmYWxzZSwgImZvcmNlIjogZmFsc2UsICJvcHMiOiBbWyJ0cmltIiwgW2ZhbHNlLCBmYWxzZV0sIHt9XSwgWyJyZXNpemUiLCBbXSwgeyJ3aWR0aCI6IDk5Ni4wLCAiYWxsb3dfdXAiOiBmYWxzZSwgImhlaWdodCI6IDk5Ni4wfV0sIFsiY2FudmFzX2NlbnRlcmVkIiwgWzEyMDAsIDEyMDBdLCB7ImJhY2tncm91bmQiOiAiZmZmZmZmIn1dLCBbInJlc2l6ZSIsIFs4MDBdLCB7fV0sIFsiY2FudmFzX2NlbnRlcmVkIiwgWzgwMCwgODAwLCAiI2ZmZmZmZiJdLCB7fV0sIFsiZW5jb2RlIiwgWyJqcGciLCA4NV0sIHt9XV19'
            : selection === 'React'
            ? 'https://c.wallhere.com/photos/02/95/reactJS_Facebook_JavaScript_minimalism_artwork_simple_background-11095.png!d'
            : 'https://tacm.com/wp-content/uploads/2018/01/no-image-available.jpeg'
        "
        :alt="selection + ' ' + 'Logo'"
      />
    </div>
  </div>
</template>

<script>
export default {
  data() {
    // Initializes selection and imageSrc variables with blank values as their default state.
    return {
      selection: "",
      imageSrc: "",
    };
  },
  methods: {
    // When invoked, this function changes the state of theh selection variable to "Angular"
    angularSelected() {
      this.selection = "Angular";
    },
    // When invoked, this function changes the state of theh selection variable to "Vue"
    vueSelected() {
      this.selection = "Vue";
    },
    // When invoked, this function changes the state of theh selection variable to "React"
    reactSelected() {
      this.selection = "React";
    },
  },
};
</script>

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