<template>
  <div class="h-screen w-full">
    <div class="">
      <p class="text-center text-3xl py-2 my-8">Login</p>
    </div>
    <v-card theme="dark" class="flex w-1/3 mx-auto">
      <LoginForm />
    </v-card>
  </div>
</template>

<script>
import LoginForm from '../components/loginForm.vue'

export default {
  components: { LoginForm }
}
</script>

<style></style>
