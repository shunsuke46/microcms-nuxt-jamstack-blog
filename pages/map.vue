<template>
    
    <ul>
      <li v-for="content in contents" :key="content.id">
        <nuxt-link :to="`/${content.id}`">
          {{ content.prefecture}}
        </nuxt-link>
      </li>
    </ul>
  </template>
  
  <script>
  import axios from 'axios'
  export default {
    async asyncData() {
      const { map } = await axios.get(
        // your-service-id部分は自分のサービスidに置き換えてください
        'https://your-service-id.microcms.io/api/v1/map',
        {
          // your-api-key部分は自分のapi-keyに置き換えてください
          headers: { 'X-API-KEY': '8c148f4c-3a95-4d30-b3ba-72d534fc42e7"' }
        }
      )
      return map
    }
  }
  </script>