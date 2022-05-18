<template>
  <main>
    <banner-image :source="'/img1.jpg'" :alt="'imagen de playa'"  />
    <section />
    <h1>Nuxt Mountains</h1>
    <div>
    <p v-if="$fetchState.pending">Fetching mountains...</p>
    <p v-else-if="$fetchState.error">An error occurred :(</p>
    <div v-else>
      <ul>
        <li v-for="mountain of mountains">{{ mountain.title }} <br> <p>{{ mountain.description }}</p></li>
      </ul>
      <button @click="$fetch">Refresh</button>
          </div>
        <div id="map-wrap" style="height:20vh" >
          <client-only>
            <l-map :zoom=13 :center="[55.9464418,8.1277591]">
              <l-tile-layer url="http://{s}.tile.osm.org/{z}/{x}/{y}.png"></l-tile-layer>
              <l-marker :lat-lng="[55.9464418,8.1277591]"></l-marker>
            </l-map>
          </client-only>
    </div>
    </div>

  </main>
</template>

<script>
export default {
  name: 'IndexPage',
  data() {
      return {
        mountains: []
      }
    },
    async fetch() {
      this.mountains = await fetch(
        'https://api.nuxtjs.dev/mountains'
      ).then(res => res.json())
    }
}
</script>
<style lang="postcss" scoped>
  ul{
    @apply ml-20 mr-28;

  }
  li p{
     @apply text-yellow-600
  }
  button{
    @apply bg-gray-300 p-3 w-40 rounded-3xl my-3 ml-20 mb-10;
    }
    button:hover{
      @apply bg-gray-500;
    }
  h1{
    @apply text-3xl ml-20 mb-10;
  }
  p{
    @apply ml-20 mr-28;
  }
  section{
    @apply p-5;
  }
</style>
