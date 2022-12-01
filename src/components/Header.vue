<template>
  <div class="nav">
      <div class="container-row">
        <img class="img-logo" src="../assets/img/logo.png" alt="">
        <div class="button-container">
          <button class="button-link"><img src="../assets/img/Person.png" alt="" ></button>
          <button class="button-link"><img src="../assets/img/Favorite.png" alt=""  @click="$emit('open')"></button>
          <button class="button-link"><img src="../assets/img/Bag.png" alt=""></button>
          <button class="button-link button-visible"><img src="../assets/img/Menu.png" alt=""></button>
        </div>
      </div>
  </div>
</template>

<script>
export default {
  emits: ['open']
}
</script>

<style>
 
</style>