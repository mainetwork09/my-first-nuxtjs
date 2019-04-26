<template>
  <div>
    <p>ID = {{ params.id }}</p>
    <p>
      <img :src="product.avatar" alt="">
    </p>
    <p>{{ product.first_name }} {{ product.last_name }}</p>
  </div>
</template>
<script>

const apiUrl = `https://reqres.in/api`

export default {
  data() {
    return {
      product: {},
      params: this.$nuxt._route.params
    }
  },
  mounted() {
    fetch(apiUrl + '/users/' + this.params.id).then((res) => {
      res.json().then((res) => {
        this.product = res.data
      })
    })
  },
  validate({ params }) {
    return /^\d+$/.test(params.id)
  }
}

</script>
