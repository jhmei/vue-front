<template>
  <ul>
    <li v-for="item in list" :key="item.id">
      {{item.id}}:{{item.name}}
    </li>
  </ul>
</template>

<script>
import axios from 'axios';

export default {
  name: 'app',
  data() {
    return {
      list: []
    }
  },
  mounted() {
    axios.get('/api/list').then(response => {
      this.list = response.data || []
    })
  }
}
</script>

<style>
</style>
