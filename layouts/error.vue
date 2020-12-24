<template>
  <div class="error-message">
    <h1>
      {{ error.statusCode }}
    </h1>

    <h2>
      {{ error.message }}
    </h2>

    <p>
      LINK later

      <!-- p(v-if='error.statusCode === 404')
                nuxt-link.error-link(to='/', title='Back to the home page')
                    | Back to the home page -->
    </p>
  </div>
</template>

<script>
export default {
  props: {
    error: {
      type: Object,
      required: true,
      default: () => ({
        message: String,
      }),
    },
  },
  head() {
    return {
      title: this.error.message || 'An error occured',
    }
  },
}
</script>

<style>
.error-message {
  background: red;
}
</style>
