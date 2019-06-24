<template lang="html">
  <li v-on:click="handleClick">{{film.title}}</li>

</template>

<script>
import { eventBus } from '../main.js'
export default {
  name: 'film-list-item',
  props: ['film'],
  methods: {
    handleClick(){
      eventBus.$emit('film-selected', this.film)
    }
  }
}
</script>

<style lang="css" scoped>
</style>


















<!-- <template lang="html">
  <div class="">
    <h2>{{film.title}}</h2>
    <button v-if="!inFavourites" v-on:click="handleButton" type="button" name="button">Details</button>
  </div>
  <!-- <li v-on:click="handleClick">{{film.title}}</li> -->

<!-- </template>

<script>
import { eventBus } from '@/main.js'
export default {
  name: 'film-list-item',
  props: ['film', 'favourites'],
  computed: {
    inFavourites: function(){
      return this.favourites.includes(this.film)
    }
  },
  methods: {
    handleButton(){
      eventBus.$emit('film-selected', this.film)
    }
  }
}
</script>

<style lang="css" scoped>
</style> --> -->
