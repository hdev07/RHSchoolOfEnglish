<template>
  <div class="h-auto m-2 my-4">
    <v-form ref="form" v-model="valid" lazy-validation>
      <div class="mx-4 py-2">
        <v-text-field
          v-model="name"
          :rules="nameRules"
          type="text"
          label="Nombre"
          required
          outlined
        />
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
        <v-text-field
          v-model="rePassword"
          :rules="rePasswordRules"
          type="password"
          label="Confirma tu contraseña"
          required
          outlined
        />
      </div>
      <div class="flex justify-between">
        <v-btn class="mx-4" outlined @click="goToLogin()"> Log in </v-btn>
        <v-btn :disabled="!valid" class="mx-4" color="primary" fill @click="validForm()">
          Create acount
        </v-btn>
      </div>
    </v-form>
  </div>
</template>

<script>
export default {
  name: 'registerForm',
  data() {
    return {
      valid: true,
      name: '',
      nameRules: [(v) => !!v || 'Nombre es requerido'],
      email: '',
      emailRules: [
        (v) => !!v || 'Correo es requerido',
        (v) => /.+@.+\..+/.test(v) || 'Correo no valido'
      ],
      password: '',
      passwordRules: [(v) => !!v || 'Contraseña es requerida'],
      rePassword: '',
      rePasswordRules: [
        (v) => !!v || 'Contraseña es requerida',
        (v) => v === this.password || 'las contraseñas no coinciden'
      ]
    }
  },
  methods: {
    async validForm() {
      const valid = await this.$refs.form.validate()
      if (valid) return this.register()
    },
    register() {
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
    goToLogin() {
      this.$router.push('/login')
    }
  }
}
</script>

<style></style>
