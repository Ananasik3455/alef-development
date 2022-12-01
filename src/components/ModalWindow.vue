<template>
 <div class="modal-backdrop" @click="$emit('close')"></div>
  <div class="modal-window">
    <div class="product-container">
      <p class="text-product">Товар "{{ name_products }}" в количестве "{{ countProducts }}" единиц добавлен в корзину/избранное</p>
    </div>
  </div>
</template>

<script>
export default {
  data() {
    return {
    }
  },
  props: {
    name_products: {
      type: String
    },
    countProducts: {
      type:  Number
    }
  },
  emits : ['close']
}
</script>

<style>

</style>