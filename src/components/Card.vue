<template>
  <a href="#" class="gz-card-link">
    <div @mouseenter="toggleHovering()" @mouseleave="toggleHovering()">
      <img :src="displayImage" alt="Imagem do produto" class="gz-card-img">
    </div>

    <div>
      <!-- Texto -->
      <div>
        <h3>{{ product.name }}</h3>
        <p class="subtitle-2">{{ product.description }}</p>
      </div>
      <!-- Preço -->
      <div class="mt-1">
        <span 
          :class="product.discount && 'text-decoration-line-through grey--text'"
        >
          R$ {{product.price}}
        </span>
        <span class="ml-3 font-weight-bold" v-if="product.discount">R$ {{ discountedPrice }}</span>
        <p class="font-weight-bold">6x de {{ minimumPayment }}</p>
      </div>
    </div>
  </a>
</template>

<script>
  export default {
    data() {
      return {
        discountedPrice: 0,
        minimumPayment: 0,
        displayImage: null,
        isHovering: false
      }
    },
    props: {
      product: {
        type: Object,
        required: true
      }
    },

      methods: {
        toggleHovering: function() {
          this.isHovering = !this.isHovering;
        },
        changeDisplayImage: function() {
          if(this.isHovering){
            this.displayImage = this.product.images[1];
          } else {
            this.displayImage = this.product.images[0];
          }
        }
      },
      watch: {
        isHovering() {
          this.changeDisplayImage();
        }
    },

    mounted() {
      // Define a imagem que será exibida no card
      this.displayImage = this.product.images[0];

      // Calcula o valor com desconto
      this.discountedPrice = this.product.price - (this.product.price * this.product.discount/100);
      // Calcula o valor da menor parcela
      if(this.discountedPrice) {
        this.minimumPayment = this.discountedPrice / 6;
      } else {
        this.minimumPayment = this.product.price / 6;
      }

      // Fixa 2 casas depois da virgula e transforma em string, todos os valores
      this.discountedPrice = this.discountedPrice.toFixed(2).toString();
      this.product.price = this.product.price.toFixed(2).toString();
      this.minimumPayment = this.minimumPayment.toFixed(2).toString()
      // Substitui o ponto pela virgula
      this.discountedPrice = this.discountedPrice.replace(".", ",");
      this.product.price = this.product.price.replace(".", ",");
      this.minimumPayment = this.minimumPayment.replace(".", ",")

      if(this.product.description.length > 10) {
        this.product.description = this.product.description.slice(0, 30) + '...';
      }
    },

  }
</script>

<style scoped>
  .gz-card-link{
    color: black;
    text-decoration: none;
  }
  .gz-card-link > div{
    transition: all ease-in-out 0.3s;
  }
  .gz-card-link:focus > div{
    background-color: #BBDEFB;
  }
  .gz-card-img{
    width: 100%;
  }
</style>