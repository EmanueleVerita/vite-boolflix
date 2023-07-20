<script>
import HeaderApp from './components/HeaderApp.vue';
import MainApp from './components/MainApp.vue';
import FooterApp from './components/FooterApp.vue';
import axios from 'axios';
import {store} from './store.js'


export default {
  components: { HeaderApp, MainApp, FooterApp },

    data() {
        return {
          store
        };
    },
    methods: {
      search() {
        console.log(this.store.searchText)

        axios.get('https://api.themoviedb.org/3/search/movie' , {
          params: {
            api_key: '1b561498f100ed73b76b73daabe965d5',
            query: this.store.searchText
          }
        })
        .then(res => {
          console.log(res.data);

          this.movies = res.data.results;
        });
      }
    }
}
</script>

<template>
  <HeaderApp @performSearch="search()"/>

  <MainApp/>

  <FooterApp/>

 
</template>

<style lang="scss">

</style>
