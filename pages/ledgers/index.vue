<template>
  <div>
    <p>LEDGERS</p>
    {{ user }}
    <div class="mt-20">
      <button @click="getLedgers()">
        ledgers
      </button>
    </div>
    <div class="mt-20">
      {{ ledgers }}
    </div>
  </div>
</template>

<script>
export default {
  name: 'IndexLedger',
  middleware: ['auth'],
  data() {
    return {
      ledgers: []
    }
  },
  computed: {
    user() {
      return this.$auth.user
    }
  },
  methods: {
    async getLedgers() {
      try {
        const url = '/ledgers'
        this.ledgers = await this.$axios.$get(url)
      } catch (e) {}
    }
  }
}
</script>

<style scoped>

</style>
