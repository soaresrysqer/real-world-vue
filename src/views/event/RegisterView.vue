<template>
  <div v-if="event">
    <p>Register Event</p>
    <button @click="register">Register Me</button>
  </div>
</template>

<script>
export default {
  props: ['event'],
  inject: ['GStore'],
  methods: {
    register() {
      this.GStore.flashMessage =
        'You are successfully registered for ' + this.event.title

      setTimeout(() => {
        this.GStore.flashMessage = ''
      }, 3000)
      this.$router.push({
        name: 'event-details',
      })
    },
  },
}
</script>
