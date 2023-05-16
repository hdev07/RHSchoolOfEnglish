<template>
  <div class="h-auto w-full">
    <div class="">
      <p class="text-center text-3xl py-2 my-8">Register</p>
    </div>
    <v-card theme="dark" class="flex w-1/3 mx-auto">
      <register-form />
    </v-card>
  </div>
</template>

<script>
import registerForm from '../components/registerForm.vue'
export default {
  components: { registerForm }
}
</script>

<style></style>
