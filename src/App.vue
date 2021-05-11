<template>
  <v-app>
    <StripHeader/>
    <PageHeader/>
    <NavBar :uniqueCategories="uniqueCategories"/>

    <Home :products="products"/>

    <PageFooter/>

    <Drawer :uniqueCategories="uniqueCategories" class="d-md-none"/>
  </v-app>

</template>

<script>
// Views
import Home from './views/Home'
// Componentes
import StripHeader from './components/StripHeader'
import PageHeader from './components/PageHeader'
import NavBar from './components/NavBar'
import PageFooter from './components/PageFooter'
import Drawer from './components/Drawer'
// Dados mocados
import products from './data/products'

export default {
  name: 'App',

  data() {
    return {
      products,
      uniqueCategories: []
    }
  },

  mounted() {
    // Separa as categorias em uma nova array
    const categoriesArray = this.products.map((product) => product.category);
    // Cria uma array de categorias unicas
    this.uniqueCategories = [...new Set(categoriesArray)];
  },

  components: {
    Home,
    StripHeader,
    PageHeader,
    NavBar,
    PageFooter,
    Drawer,
  },

};
</script>

<style>
  .gz-mw-md{
    max-width: 1264px;
  }
</style>