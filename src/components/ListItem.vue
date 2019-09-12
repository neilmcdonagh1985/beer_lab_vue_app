<template lang='html'>
  <li v-on:click="handleClick">{{beer.name}}
    <button v-on:click="markAsFavourite()">Add to favourites</button>
  </li>
</template>

<script>
import { eventBus } from '../main.js'

export default {
    name: 'list-item',
    props: ['beer'],
    methods: {
        handleClick() {
            eventBus.$emit('beer-selected', this.beer)
        },
        markAsFavourite() {
            eventBus.$emit('favourite-beer', this.beer)
        }
    }
}
</script>

<style lang='css' scoped>

</style>