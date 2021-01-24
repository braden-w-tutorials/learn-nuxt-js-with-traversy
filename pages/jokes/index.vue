<template>
  <div>
    <h2>Jokes List</h2>
  </div>
</template>
<script>
export default {
  data() {
    return {
      jokes: [],
    }
  },
  head() {
    return {
      title: 'Jokes',
      meta: [
        {
          hid: 'description',
          name: 'description',
          content: 'Best place for corny dad jokes',
        },
      ],
    }
  },
  created() {},
}
</script>

<style></style>
