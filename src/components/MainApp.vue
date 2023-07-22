<script>
import {store} from '../store.js';
import SingleElementApp from './SingleElementApp.vue';

export default {
  data() {
    return {
      store,
    }
  },
  components: {

    SingleElementApp

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
        <SingleElementApp :elementData="movie"/>
        
      </li>
    </ul>

    <h2>
        SERIES
    </h2>

    <hr>

    <ul>
      <li v-for="(singleSeries , i) in store.series" :key="i">
        <SingleElementApp :elementData="singleSeries"/>
        
      </li>
    </ul>
  </main>
</template>



<style lang="scss">

    img{
        width: 40px;
    }

</style>