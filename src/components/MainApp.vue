<script>
import {store} from '../store.js'

export default {
  data() {
    return {
      store,
    }
  }
}
</script>




<template>
      <main>
    <ul>
      <li v-for="(movie , i) in store.movies" :key="i">
        <ol>
          <li>
            {{ movie.title }}
          </li>

          <li>
            {{ movie.original_title }}
          </li>

          <li>
            {{ movie.original_language }}
          </li>

          <li>
            {{ movie.vote_average }}
          </li>
        </ol>
      </li>
    </ul>
  </main>
</template>



<style lang="scss">

</style>