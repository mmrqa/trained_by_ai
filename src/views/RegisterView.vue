<script setup>
import Login from "../components/Login.vue";
import Register from "../components/Register.vue";
</script>

<template>
  <div id="regview" class="d-flex flex-column align-items-center justify-content-center h-100">
    <div class="text-center mt-5" id="header">
      <h2>Muscels from AI - Strength your body with computed intelligence</h2>
      <p class="lead">
        {{ regtext }}
      </p>
      <hr class="mt-4" />
    </div>
    <div class="btn-group mb-4" role="group" aria-label="Basic example">
      <button class="btn btn-success" @click="register">Register</button>
      <button class="btn btn-outline-success" @click="login">Login</button>
    </div>
    <Register v-if="mode === 'register'" />
    <Login v-else />

  </div>
</template>
<script>
export default { 
  data() { 
    return { 
      mode: 'register',
      regtext: "Sign-Up to check out your individual workout plan created by AI." }
  }, 
  methods:{
    register(){
      this.mode = 'register';
      this.regtext = "Sign-Up to check out your individual workout plan created by AI."
    },
    login(){
      this.mode = 'login';
      this.regtext = "Good to have you back. Just type your mail and use the authentification from your operating system."
    }
  }
}
</script>
