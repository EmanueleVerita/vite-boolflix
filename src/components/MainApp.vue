<script>
import {store} from '../store.js'

export default {
  data() {
    return {
      store,
    }
  },
  methods:{
    getFlag(lang){
        if(lang == 'it'){

            return 'https://flagicons.lipis.dev/flags/4x3/it.svg';

        }
       
        else if(lang == 'en'){

            return 'https://flagicons.lipis.dev/flags/4x3/gb.svg';

        }
        

        else{

            return 'https://flagicons.lipis.dev/flags/4x3/un.svg';

        }
    }
  }
}
</script>




<template>
      <main>
        <h2>
            MOVIES
        </h2>

        <hr>


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
            <img :src="getFlag(movie.original_language)" alt="">
            
          </li>

          <li>
            {{ movie.vote_average }}
          </li>
        </ol>
      </li>
    </ul>

    <h2>
        SERIES
    </h2>

    <hr>

    <ul>
      <li v-for="(singleSeries , i) in store.series" :key="i">
        <ol>
          <li>
            {{ singleSeries.name }}
          </li>

          <li>
            {{ singleSeries.original_name }}
          </li>

          <li>
            <img :src="getFlag(singleSeries.original_language)" alt="">
            
          </li>

          <li>
            {{ singleSeries.vote_average }}
          </li>
        </ol>
      </li>
    </ul>
  </main>
</template>



<style lang="scss">

    img{
        width: 40px;
    }

</style>