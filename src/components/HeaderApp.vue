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
  <header>
    <input type="text" placeholder="cerca..." v-model="store.searchText">
    <button @click="$emit('performSearch')">
      Cerca
    </button>
  </header>
</template>



<style lang="scss">

</style>