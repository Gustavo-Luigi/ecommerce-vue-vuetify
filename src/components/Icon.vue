<template>
  <v-icon class="gz-icon">{{ iconName }}</v-icon>
</template>

<script>
  export default {
    props: {
      iconName: {
        type: String,
        required: true
      }
    }
  }
</script>

<style scoped>
  .gz-icon:hover{
    color: #2962FF;
  }
</style>