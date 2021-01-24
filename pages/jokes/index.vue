<template>
  <div>
    <SearchJoke @search-text="searchText" />
    <h2>Jokes List</h2>
    <Joke
      v-for="joke in jokes"
      :id="joke.id"
      :key="joke.id"
      :joke="joke.joke"
    />
  </div>
</template>
<script>
import axios from 'axios'
import Joke from '@/components/Joke.vue'
import SearchJoke from '@/components/SearchJoke.vue'

export default {
  components: { Joke, SearchJoke },
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
  async created() {
    const config = {
      headers: { Accept: 'application/json' },
    }

    try {
      const res = await axios.get('https://icanhazdadjoke.com/search', config)
      this.jokes = res.data.results
      console.log(this.jokes)
    } catch (err) {
      console.error(err)
    }
  },
  methods: {
    async searchText(text) {
      console.log('Clicked')
      const config = {
        headers: { Accept: 'application/json' },
      }

      try {
        const res = await axios.get(
          `https://icanhazdadjoke.com/search?term=${text}`,
          config
        )
        this.jokes = res.data.results
        console.log(this.jokes)
      } catch (err) {
        console.error(err)
      }
    },
  },
}
</script>

<style></style>
