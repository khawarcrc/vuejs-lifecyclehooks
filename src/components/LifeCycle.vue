<template>
  <h2>Life Cycle</h2>
  <button @click="initialCount">++</button>
  <div>{{ initial }}</div>
  <div>{{ message }}</div>

  <!--Created  -->
  <!-- When this hook is called, the following have been set up: reactive data,
  computed properties, methods, and watchers. However, the mounting phase has
  not been started, and the $el property will not be available yet. -->
</template>
<script>
export default {
  props: [],
  data() {
    return {
      initial: 0,
      message: "",
      computedPropertMessage: "Computed property runs before created",
      createdMessage: "Hello component at created stage",
    };
  },
  methods: {
    initialCount() {
      this.initial++;
    },
  },
  //  BeforeCreate
  //       perform actions before the component instance is created.
  //     Called immediately when the instance is initialized, after props resolution,
  //     before processing other options such as data() or computed.
  //     Note that the setup() hook of Composition API is called before any Options API hooks, even beforeCreate().
  beforeCreate() {
    this.message = "This is message set in before create hook";
    console.log("triggered before create");
  },
  created() {
    // This is called when the component is created, but it's not mounted to the DOM yet.
    // You can initialize data, but you can't access DOM elements.
    console.log("component created");
    setTimeout(() => {
      this.message = "Hello, Vue! (Data updated after component creation)";
    }, 2000);
  },
  mounted() {
    // This is called after the component has been mounted to the DOM.
    // You can access DOM elements and perform operations that require the component to be visible.
  },
};
</script>

<style lang="scss" scoped></style>
