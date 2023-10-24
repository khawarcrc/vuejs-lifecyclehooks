<template>
  <!-- Display the value of the 'msg' prop in an <h1> element -->
  <h1>{{ msg }}</h1>

  <div class="card">
    <!-- Display a button and bind a click event to the 'incrementCount' method -->
    <button @click="count++">Incrememnt</button>
    <span>{{ count }}</span>
    <button @click="decrementCount">Decrement</button>
    <!-- Display the current value of the 'count' variable -->
  </div>
</template>

<script>
export default {
  // Define the component and specify its props
  props:['msg',],
  // props: {
  //   msg: String,
  // },
  // Define the component's data using the 'data' option
  data() {
    return {
      count: 0, // Initialize the 'count' variable with a value of 0
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
  },
};
</script>
