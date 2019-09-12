<template lang='html'>
  <div v-if="beer">
      <h2>{{beer.name}}</h2>
      <h3>{{beer.tagline}}</h3>
      <div>
          <img :src="beer.image_url" :alt="beer.name">
        </div>
    </div>
</template>

<script>
export default {
    name: 'beer-detail',
    props: ['beer']
}
</script>

<style lang='css' scoped>

</style>