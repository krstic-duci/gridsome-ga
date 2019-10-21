<template>
  <div class="cookie-consent">
    <p>Some yada yada text about cookie policy</p>
    <button @click="enableAnalytics">I agree</button>
    <button @click="disableAnalytics">No, thanks</button>
  </div>
</template>

<script>
export default {
  name: 'cookieConsent',
  methods: {
    enableAnalytics () {
      this.$ga.enable()
      localStorage.setItem('isAnalyticLoaded', 'true')
    },
    disableAnalytics () {
      this.$ga.disable()
      localStorage.setItem('isAnalyticLoaded', 'false')
    }
  }
}
</script>

<style scoped>
  .cookie-consent {
    position: fixed;
    bottom: 0;
    width: 100%;
    background-color: bisque;
    text-align: center;
    z-index: 150;
  }
</style>