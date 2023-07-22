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
          store,
          apiKey: '1b561498f100ed73b76b73daabe965d5'
        };
    },
    methods: {
      search() {
        console.log(this.store.searchText)

        axios.get('https://api.themoviedb.org/3/search/movie' , {
          params: {
            api_key: this.apiKey,
            query: this.store.searchText
          }
        })
        .then(res => {
          console.log(res.data);

          this.store.movies = res.data.results;
        });

        axios.get('https://api.themoviedb.org/3/search/tv' , {
          params: {
            api_key: this.apiKey,
            query: this.store.searchText
          }
        })
        .then(res => {
          console.log(res.data);

          this.store.series = res.data.results;
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
