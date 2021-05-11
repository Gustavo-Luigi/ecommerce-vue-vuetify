<template>
  <div :class="drawer && 'open'">
    <nav class="gz-mob-nav-container">
      <ul class="gz-nav-ul">
        <li v-for="(category, index) in uniqueCategories" :key="index" >
          <a href="#">{{ category }}s</a>
        </li>
      </ul>
    </nav>

    <v-container class="orange darken-1 rounded-circle gz-ham-container" @click="drawer =  !drawer">
      <v-icon class="gz-ham-icon">mdi-menu</v-icon>
    </v-container>
  </div>
</template>

<script>

  export default {
    data() {
      return {
        drawer: false
      }
    },
    props: {
      uniqueCategories: {
        type: Array,
        required: true
      }
    },
  }

</script>

<style scoped>
  .gz-mob-nav-container{
    position: fixed;
    right: 0;
    bottom: 0;
    width: 0;
    height: 50%;
    background-color: white;
    border-radius: 20px;
    overflow: hidden;
    z-index: 2;
    transition: all ease-in-out 0.3s;
  }
  .open .gz-mob-nav-container{
    width: 70%;
  }
  .gz-nav-ul{
    padding: 0;
    list-style: none;
    width: 100%;
  }

  a{
    display: block;
    text-align: center;
    padding: 1rem 0;
    color: black !important;
    text-decoration: none;
    margin: auto;
    border-bottom: 1px solid #ccc;
    text-transform: uppercase;
    letter-spacing: 2px;
  }

.gz-ham-container{
    position: fixed;
    bottom: 20px;
    left: 20px;
    width: 60px;
    height: 60px;
    z-index: 5;
  }
  .gz-ham-icon{
    position: absolute;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%);
    font-size: 40px;
    cursor: pointer;
  }


</style>