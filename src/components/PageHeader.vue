<template>
  <v-container fluid class="">
    <v-container tag='header' class="gz-mw-md py-5">
      <v-row class="">
        <!-- Logomarca -->
        <v-col 
          cols='12'
          :sm="3"
        >
          <a href="#">
            <Logo/>
          </a>
        </v-col>

        <!-- Barra de pesquisa -->
        <v-col 
          cols='12'
          :sm="6"
          style="position: relative"
        >
          <v-form>
            <v-text-field
              hide-details
              prepend-icon="mdi-magnify"
              single-line
              aria-label='Procurar produtos'
              style='max-width: 340px'
              class="mx-auto"
            />
          </v-form>
        </v-col>

        <!-- Login, carrinho e lista de desejos -->
        <v-col class="text-right-sm-and-up text-center" cols='12' :sm='3'>
          <v-row>
              <v-col>
                <a href="#" aria-label='Entre ou cadastre-se'>
                  <Icon iconName="mdi-account"/>
                </a>
              </v-col>

              <v-col>
                <a href="#" aria-label='Lista de desejos'>
                  <Icon iconName="mdi-heart"/>
                </a>
              </v-col>

              <v-col>
                <a href="#" aria-label='Carrinho' >
                  <Icon iconName="mdi-cart"/>
                </a>
              </v-col>
          </v-row>
        </v-col>

      </v-row>
    </v-container>
  </v-container>
</template>

<script>
  import Logo from './Logo'
  import Icon from './Icon'

  export default {
    components: {
      Logo,
      Icon
    }
  }
</script>