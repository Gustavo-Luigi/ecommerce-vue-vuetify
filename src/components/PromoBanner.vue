<template>
  <v-container class="gz-mw-md gz-banner-container">
    <v-carousel cycle>
      <v-carousel-item
        v-for="(carouselItem, index) in carouselItens"
        :key="index"
      >
        <v-sheet
          height="100%"
          tile
        >
          <v-row
            class="fill-height"
            align="center"
            justify="center"
          >
            <div class="display-3">
              <a href="#" :aria-label="carouselItem.alt">
                <picture >
                    <source :srcset="carouselItem.mdUrl" media="(min-width: 600px)" class="gz-banner-img">
                    <img :src="carouselItem.smUrl" :alt="carouselItem.alt" class="gz-banner-img">
                </picture>
              </a>
            </div>
          </v-row>
        </v-sheet>
      </v-carousel-item>
    </v-carousel>
  </v-container>
</template>

<script>
  export default {
    data() {
      return {
        carouselItens: [
          {
            mdUrl: require('../assets/50off-md.jpg'),
            smUrl: require('../assets/50off-sm.jpg'),
            alt: 'Produtos com até 50% de desconto'
          },
          {
            mdUrl: require('../assets/sale-md.jpg'),
            smUrl: require('../assets/sale-sm.jpg'),
            alt: 'Produtos com até 50% de desconto'
          },
        ]
      }
    },
    
  }
</script>

<style scoped>
  .gz-banner-container{
    max-height: 500px;
    overflow: hidden;
  }

  .gz-banner-img{
    display: block;
    height: 100%;
    object-fit: scale-down;
  }
</style>