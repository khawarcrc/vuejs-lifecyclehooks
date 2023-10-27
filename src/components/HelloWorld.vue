<template>
  <!-- Display the value of the 'msg' prop in an <h1> element -->
  <h2>{{ msg }}</h2>

  <div class="card">
    <!-- Display a button and bind a click event to the 'incrementCount' method -->
    <button @click="count++">Incrememnt</button>
    <span>{{ count }}</span>
    <button @click="decrementCount">Decrement</button>
    <!-- Display the current value of the 'count' variable -->
  </div>
  <div>
    <button @click="concatWord">concate data</button>
    {{ someVariable }}
    <button @click="removeConcat">remove concat</button>
  </div>

<!-- computed properties -->
<!-- watchers -->
</template>

<script>
export default {
  // Define the component and specify its props
  props: ["msg"],
  // props: {
  //   msg: String,
  // },
  // Define the component's data using the 'data' option
  data() {
    return {
      count: 0, // Initialize the 'count' variable with a value of 0
      someVariable: "abc",
    };
  },

  // Define the component's methods
  methods: {
    // Define a method called 'incrementCount'
    incrementCount() {
      this.count++; // Increment the 'count' variable by 1
    },
    decrementCount() {
      this.count--;
    },
    concatWord() {
      this.someVariable += "abc2";
    },
    removeConcat() {
      if (this.someVariable.length > 3) {
        this.someVariable = this.someVariable.slice(0, -4);
      }
    },
  },
};
</script>
