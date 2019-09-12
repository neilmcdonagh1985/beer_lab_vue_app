<template lang="html">
    <div>
      <h1>Brewdog Beers</h1>
      <div>
        <beer-list :beers="beers"></beer-list>
        <list-item :beer="beer"></list-item>
      </div>
    </div>
</template>

<script>
import ListItem from './components/ListItem.vue'
import BeerList from './components/BeerList.vue'
import { eventBus } from './main.js'


export default {
  name: 'app',
  data(){
    return {
      beers: [],
      selectedBeer: null}
    },
  components: {
      "beer-list": BeerList,
      "list-item": ListItem
  },
  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(res => res.json())
    .then(beers => this.beers = beers)
  }
  
}
</script>

<style lang="css" scoped>

</style>