<template>
  <v-container fluid class="gz-border-tb py-0">
    <v-container tag='nav' class="gz-mw-md d-flex py-0">
      <ul class="gz-nav-ul hidden-sm-and-down">
        <li v-for="(category, index) in uniqueCategories" :key="index" >
          <a href="#">{{ category }}s</a>
        </li>
      </ul>
      
    </v-container>
  </v-container>
</template>

<script>

  export default {
    props: {
      uniqueCategories: {
        type: Array,
        required: true
      }
    },
  }

</script>

<style scoped>
  .gz-border-tb{
    border-top: 1px solid #ccc;
    border-bottom: 1px solid #ccc;
  }
  .gz-nav-ul{
    display: flex;
    width: 100%;
    list-style: none;
    padding: 0;
    justify-content: center;
  }

  a{
    position: relative;
    display: inline-block;
    padding: 1rem;
    text-decoration: none;
    text-transform: uppercase;
    letter-spacing: 2px;
    color: black !important;
    z-index: 2;
  }
  a::before{
    content: '';
    position: absolute;
    width: 100%;
    height: 100%;
    top: 50%;
    left: 50%;
    transform: translate(-50%, -50%) skew(0) scale(0, 100%);
    transition: transform ease-in-out 0.3s;
    background-color: #E3F2FD;
    z-index: -1;
  }

  a:hover::before, a:focus::before{
    transform: translate(-50%, -50%) skew(20deg) scale(100%, 100%);
  }

  a{
    outline: none;
  }
</style>