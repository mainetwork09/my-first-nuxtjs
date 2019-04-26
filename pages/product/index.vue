<template>
  <div>
    <h1>Products</h1>
    <div v-for="item in items" :key="item">
      <p><nuxt-link :to="{ path: 'product/'+item.id }">{{ item.id }} {{ item.first_name }}</nuxt-link></p>
    </div>
  </div>
</template>

<script>

const apiUrl = `https://reqres.in/api`

export default {
  debug: true,
  data() {
    return {
      items: {}
    }
  },
  mounted() {
    fetch(apiUrl + '/users').then((res) => {
      res.json().then((res) => {
        this.items = res.data
      })
    })
  }
}

</script>
