<template>
  <div>
    <div>
      <label for="name">Name:</label>
      <input v-model="formData.name" id="name" type="text" />
    </div>
    <div>
      <label for="email">Email:</label>
      <input v-model="formData.email" type="email" id="email" />
    </div>
    <div>
      <label for="password">Password:</label>
      <input v-model="formData.password" type="password" id="password" />
    </div>
    <div>
      <label for="phone">Phone:</label>
      <input v-model="formData.phone" type="phone" id="phone" />
    </div>
    <div>
      <label for="address">Address:</label>
      <input v-model="formData.address" id="address" />
    </div>
    <div>
      <label for="message">Message:</label>
      <input v-model="formData.message" id="message" />
    </div>
    <button @click="sendData">Send</button>
  </div>
</template>

<script setup lang="ts">
// Importing necessary functions from the Vue library
import { ref, defineEmits } from "vue";

// Creating an 'emit' function using 'defineEmits' to emit custom events
const emit = defineEmits();

// Defining an interface 'FormData' to describe the shape of the data object
interface FormData {
  name: string;
  email: string;
  password: string;
  phone: string;
  address: string;
  message: string;
}

// Creating a reactive reference 'formData' to store the form data, initializing with empty values
const formData = ref<FormData>({
  name: "",
  email: "",
  password: "",
  phone: "",
  address: "",
  message: "",
});

// Defining a function 'sendData' that emits a custom event with the form data when called
const sendData = () => {
  // Emitting the 'formData' event with the current value of 'formData'
  emit("formData", formData.value);
};
</script>

<style scoped></style>
