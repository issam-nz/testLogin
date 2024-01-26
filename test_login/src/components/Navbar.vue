<template>
    <div>
        <!-- <nav>
        <RouterLink to="/">Home</RouterLink>
        <RouterLink to="/about">About</RouterLink>
        <RouterLink to="/Login">Login</RouterLink>
        <RouterLink to="/Register">Register</RouterLink>
      </nav> -->
      <nav>
    <div class="">
      <div class="flex justify-between h-16 px-10 shadow items-center">
        <div class="flex items-center space-x-8">
          <h1 class="text-xl lg:text-2xl font-bold cursor-pointer">Tailwind</h1>
          <div class="hidden md:flex justify-around space-x-4">
            <RouterLink to="/" class="hover:text-indigo-600 text-gray-700">Home</RouterLink>
            <RouterLink to="/about" class="hover:text-indigo-600 text-gray-700">About</RouterLink>
            <!-- <a href="#" class="hover:text-indigo-600 text-gray-700">Service</a> -->
            <!-- <a href="#" class="hover:text-indigo-600 text-gray-700">Contact</a> -->
          </div>
        </div>
         <!-- Conditionally render content based on isLoggedIn -->
         <template v-if="!isLoggedIn">
            <RouterLink to="/Login" class="text-gray-800 text-sm">LOGIN</RouterLink>
            <RouterLink to="/Register" class="bg-indigo-600 px-4 py-2 rounded text-white hover:bg-indigo-500 text-sm">SIGNUP</RouterLink>
          </template>
          <template v-else>
            <div class="flex items-center space-x-4">
              <span class="text-gray-800 text-sm">Welcome, {{ usuario.nombre }}</span>
              <button @click="handleSignOut" class="bg-red-500 px-4 py-2 rounded text-white hover:bg-red-400 text-sm">SIGN OUT</button>
            </div>
          </template>
      </div>
    </div>
  </nav>
    </div>
</template>
<script>
import { RouterLink } from 'vue-router';

export default {
  name: 'Navbar',
  components: {
    RouterLink,
  },
  computed: {
    isLoggedIn() {
      return this.$store.getters.isLoggedIn;
    },
    usuario() {
      return this.$store.getters.usuarioData;
    },
  },
  methods: {
    handleSignOut() {
      this.$store.dispatch('logout');
    },
  },
}
</script>
<style lang="">
    
</style>