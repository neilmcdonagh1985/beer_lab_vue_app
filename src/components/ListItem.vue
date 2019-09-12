<template lang='html'>
  <li>{{beer.name}}</li>
</template>

<script>
import { eventBus } from '../main.js'

export default {
    name: 'list-item',
    props: ['beer'],
    methods: {}
    

}
</script>

<style lang='css' scoped>

</style>