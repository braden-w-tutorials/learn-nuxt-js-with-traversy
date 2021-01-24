<template>
  <div class="joke">
    <p>{{ joke }}</p>

    <nuxt-link :to="'/jokes/' + id">
      <v-btn>Click Me for ID</v-btn>
    </nuxt-link>
  </div>
</template>

<script>
export default {
  name: 'Joke',
  props: ['joke', 'id'],
}
</script>

<style></style>
