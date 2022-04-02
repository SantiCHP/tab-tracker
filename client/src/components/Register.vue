<template>
  <div class="register">
    <h1>Register</h1>
    <input
      type="email"
      name="email"
      placeholder="email"
      v-model="email"
    />
    <br>
    <input
      type="password"
      name="password"
      placeholder="password"
      v-model="password"
    />
    <br>
    <button
      @click="register">
      Register
    </button>
  </div>
</template>

<script>
import AuthService from '@/services/AuthenticationService'
export default {
  data () {
    return {
      email: '',
      password: ''
    }
  },
  methods: {
    async register () {
      await AuthService.register({
        email: this.email,
        password: this.password
      })
    }
  },
  mounted () {}
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
.register {
  max-width: 500px;
  margin: 0 auto;
}
</style>
