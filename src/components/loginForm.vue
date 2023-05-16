<template>
  <div class="h-auto m-2 my-4">
    <v-form ref="form" v-model="valid" lazy-validation>
      <div class="mx-4 py-4">
        <v-text-field
          v-model="email"
          :rules="emailRules"
          type="email"
          label="Correo"
          required
          outlined
        />
        <v-text-field
          v-model="password"
          :rules="passwordRules"
          type="password"
          label="Contraseña"
          required
          outlined
        />
      </div>
      <div class="flex justify-between">
        <v-btn class="mx-4" outlined @click="goToRegrister()"> Sign in </v-btn>
        <v-btn :disabled="!valid" class="mx-4" color="primary" fill @click="validForm()">
          Log in
        </v-btn>
      </div>
    </v-form>
  </div>
</template>

<script>
export default {
  name: 'loginForm',
  data() {
    return {
      valid: true,
      email: '',
      emailRules: [
        (v) => !!v || 'Correo es requerido',
        (v) => /.+@.+\..+/.test(v) || 'Correo no valido'
      ],
      password: '',
      passwordRules: [(v) => !!v || 'Contraseña es requerida']
    }
  },
  methods: {
    async validForm() {
      const valid = await this.$refs.form.validate()
      if (valid) return this.login()
    },
    login() {
      try {
        return this.$router.push('/chats')
      } catch (e) {
        console.error('no coinciden las credenciales')
      } finally {
        this.resetFrom()
      }
    },
    resetForm() {
      this.$refs.form.reset()
    },
    goToRegrister() {
      this.$router.push('/register')
    }
  }
}
</script>

<style></style>
