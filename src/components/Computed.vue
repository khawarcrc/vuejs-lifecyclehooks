<template>
  <div>
    <p>{{ message }}</p>
    <p>{{ reservedMessage }}</p>
  </div>
</template>

<script>
export default {
  prop: [],
  data() {
    return {
      message: "hello",
    };
  },
  computed: {
    // This computed property depends on the 'message' data property.
    // It will be automatically re-evaluated whenever 'message' changes.
    reservedMessage() {
      return this.message.split("").reverse().join("");
    },
  },
};
</script>

<style lang="scss" scoped></style>
