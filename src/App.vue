<template lang="html">
    <div>
      <h1>Brewdog Beers</h1>
      <div>
        <beer-list :beers="beers"></beer-list>
        <beer-detail :beer="selectedBeer"></beer-detail>
      </div>
    </div>
</template>

<script>
import { eventBus } from './main.js'
import BeerDetail from './components/BeerDetail.vue'
import ListItem from './components/ListItem.vue'
import BeerList from './components/BeerList.vue'


export default {
  name: 'app',
  data(){
    return {
      beers: [],
      selectedBeer: null,
      favourites: []
      }
    },
  components: {
      "beer-list": BeerList,
      "beer-detail": BeerDetail,
      "list-item": ListItem
  },
  mounted(){
    fetch('https://api.punkapi.com/v2/beers')
    .then(res => res.json())
    .then(beers => this.beers = beers)

    eventBus.$on('beer-selected', (beer) => {
      this.selectedBeer = beer
    }),
    eventBus.$on('favourite-beer', (beer) => {
      this.selectedBeer = beer
      favourites.push(this.selectedBeer)   
    })
  }
  
}
</script>

<style lang="css" scoped>

</style>