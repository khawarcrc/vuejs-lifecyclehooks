<!-- ParentComponent.vue -->
<template>
  <!-- Parent component template -->
  <div>
    <!-- Include the ChildComponent and listen for the 'formData' event -->
    <ChildComponent @formData="receiveFormDataFromChild" />

    <!-- Display data received from the child component -->
    <p>Data from child: {{ receivedData.name }} (Name)</p>
    <p>Data from child: {{ receivedData.password }} (Password)</p>
    <p>Data from child: {{ receivedData.email }} (Email)</p>
    <p>Data from child: {{ receivedData.phone }} (Phone)</p>
    <p>Data from child: {{ receivedData.address }} (Address)</p>
    <p>Data from child: {{ receivedData.message }} (Message)</p>
  </div>
</template>

<script setup>
// Importing ChildComponent and the 'ref' function from Vue
import ChildComponent from "./ChildComponent.vue";
import { ref } from "vue";

// Define a reactive reference to store the received data from the child component
const receivedData = ref({
  name: '',
  password: '',
  email: '',
  phone: '',
  address: '',
  message: '',
});

// Define a method to receive data from the child component
const receiveFormDataFromChild = (data) => {
  // Update the 'receivedData' reference with the data received from the child
  receivedData.value = data;

  // Log the received data to the console
  console.log("Received Data from Child:", data);
};
</script>

<style scoped></style>
