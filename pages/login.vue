<template>
  <div>
    <p>Loading</p>
  </div>
</template>

<script>
export default {
  // eslint-disable-next-line vue/multi-word-component-names
  name: 'Login',
  data: () => ({
    state: '',
    code: ''
  }),
  mounted () {
    // eslint-disable-next-line no-empty
    const clientId = process.env.AUTH0_CLIENT_ID
    const AUTH0_DOMAIN = process.env.AUTH0_DOMAIN
    console.log(1, this.$auth.$state.loggedIn, this.$route.query.state, clientId, AUTH0_DOMAIN)
    window.setTimeout(() => this.login(), 500)
    // if (this.$auth.$state.loggedIn || this.$route.query.state) {
    //
    // } else {
    //   this.$gtm.push({ event: 'start_login', isLogged: this.$auth.loggedIn, userId: '' })
    //   window.setTimeout(() => this.login(), 500)
    // }
  },
  methods: {
    async login () {
      try {
        const response = await this.$auth.loginWith('auth0')
      } catch (err) {
      }
    }
  }
}
</script>

<style>

</style>
