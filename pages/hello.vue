<template>
  <div>
    <h1>Hello {{ name }}</h1>
    <v-layout row wrap class="mb-2">
      <v-flex v-for="item in items" :key="item" xs12 sm4>
        <v-card class="ma-2">
          <v-img :src="item.image" aspect-ratio="2.75" />
          <v-card-title primary-title>
            <div>
              <h3 class="headline mb-0">
                {{ item.title }}
              </h3>
              <div>{{ item.description }}</div>
            </div>
          </v-card-title>
        </v-card>
      </v-flex>
    </v-layout>
  </div>
</template>
<script>
export default {
  data() {
    return {
      name: `Mai`,
      items: [
        {
          image: `https://cdn.vuetifyjs.com/images/cards/desert.jpg`,
          title: `Kangaroo Valley Safari`,
          description: `card_text`
        },
        {
          image: `https://cdn.vuetifyjs.com/images/cards/desert.jpg`,
          title: `Kangaroo Valley Safari World`,
          description: `card_text`
        },
        {
          image: `https://cdn.vuetifyjs.com/images/cards/desert.jpg`,
          title: `Kangaroo Valley Safari World`,
          description: `card_text`
        }
      ]
    }
  }
}

</script>
