<template>
  <v-container fluid tag="footer" class="blue lighten-4">
    <v-container class="gz-mw-md">
      <v-row>
        <!-- Logo e midias sociais -->
        <v-col
          cols="12"
          sm="3"
        >
          <!-- Logo -->
          <v-row>
            <v-col cols="12">
              <Logo/>
            </v-col>

            <!-- Midia sociais -->

            <v-col></v-col>

            <v-col cols="2">
              <a href="#" aria-label="Facebook">
                <Icon iconName="mdi-facebook" />
              </a>
            </v-col>

            <v-col cols="2">
              <a href="#" aria-label="Instagram">
                <Icon iconName="mdi-instagram" />
              </a>
            </v-col>

            <v-col></v-col>
          </v-row>
        </v-col>

        <v-spacer></v-spacer>
        <!-- Formas de pagamento -->
        <v-col
          cols="12"
          sm="6"
          md="3"
        >
          <v-row>
            <v-col cols="12">
              <h2>Formas de pagamento</h2>
            </v-col>

            <!-- Cartões -->
            <v-col v-for="paymentMethod in paymentMethods" :key="paymentMethod.name">
              <img :src="paymentMethod.imgUrl" :alt="paymentMethod.name" style="width: 100%">
            </v-col>
          </v-row>
        </v-col>

        <!-- Institucional -->
        <v-col
          cols="12"
          sm="3"
          class="gz-institucional"
        >
          <h3 class="mb-4">Institucional</h3>
          <ul>
            <li class="mb-2">
              <a href="#">Quem somos</a>
            </li>
            <li class="mb-2">
              <a href="#">Política de privacidade</a>
            </li>
            <li class="mb-2">
              <a href="#">Trabalhe conosco</a>
            </li>
          </ul>
        </v-col>
      </v-row>
    </v-container>
  </v-container>
</template>

<script>
  import Logo from './Logo'
  import Icon from './Icon'
  import paymentMethods from '../data/paymentMethods'

  export default {
    data() {
      return {
        paymentMethods
      }
    },
    components: {
      Logo,
      Icon
    } 
  }
</script>

<style scoped>
  ul{
    list-style: none;
    padding: 0;
  }

  a{
    color: black !important;
    text-decoration: none;
  }
  .gz-institucional{
    text-align: center;
  }
</style>