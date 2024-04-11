<script setup>
import { ref } from 'vue';
const userData = ref({
  email: '',
  password: '',
})
const submitForm = () => {
  localStorage.setItem('userData', JSON.stringify(userData.value));
};
</script> 
<template>
  <div class="container-fluid">
    <form class="mx-auto" @submit.prevent="submitForm">
      <div class="text-center fs-2">Login</div>
      <div class="mb-3 mt-4">
        <label class="form-label">Email address</label>
        <input type="email" class="form-control" id="exampleInputEmail1" aria-describedby="emailHelp"
          placeholder="Enter Your Email" v-model="userData.email">
        <div id="emailHelp" class="form-text">We'll never share your email with anyone else.</div>
      </div>
      <div class="mb-3">
        <label for="exampleInputPassword1" class="form-label">Password</label>
        <input type="password" class="form-control" id="exampleInputPassword1" placeholder="Enter Your Password"
          v-model="userData.password">
      </div>
      <button type="submit" class="btn btn-primary">Submit</button>
    </form>
  </div>
</template>
<style>
@import url('assets/style.css');
</style>



