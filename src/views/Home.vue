<template>
  <v-main>
    <PromoBanner/>
      <v-container tag="section" class="gz-mw-md">
        <v-row>
          <v-col
            v-for="product in products" 
            :key="product.id" 
            cols="6" 
            :sm="4"
            :md="3"
            class="mt-5">
            <Card :product="product" />
          </v-col>

        </v-row>
      </v-container>
  </v-main>
  
</template>

<script>
  import PromoBanner from '../components/PromoBanner'
  import Card from '../components/Card'

  export default {
    components: {
      PromoBanner,
      Card
    },

    props: {
      products: {
        type: Array,
        required: true
      }
    }
  }
</script>