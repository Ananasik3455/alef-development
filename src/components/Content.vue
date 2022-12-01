<template>
  <div>
    <div class="container-product">
      <div class="img-product">
        <div class="slide-img">
          <img 
            v-for="nameImg in arrFileNames"
            :key="nameImg.id"
            :src="require('../assets/img/' + nameImg.fileNameMini + '.png')" 
            @click="ChangeImg(nameImg)"
            class="mini-img"  
            :class="selectedFileName == nameImg.fileName ? 'img-opacity' : ' '">
         </div>
        <img :src="dynamicImg" alt="" class="preview-img">
      </div>
      <div class="imformation-product">
        <p class="name-product">{{ nameProduct }}</p>
        <p class="article-product">Арт. 02765/46</p>
        <div class="feedback-product">
          <p class="title-feedback">Отзывы</p>
          <div class="goods-rating">
            <span class="active"></span>	
            <span class="active"></span>    
            <span class="active"></span>  
            <span class="active"></span>    
            <span></span>
          </div>
          <a class="link-feedback" href="#">14 отзывов <img class="img-link-feedback" src="../assets/img/arrow.png" alt=""></a>
        </div>

        <div class="price-product">
          <p class="price">800 ₽</p>
          <p class="old-price">1 500 ₽</p>
          <img class="img-price" src="../assets/img/arrow.png" alt="">
        </div>

        <div class="discount-product">
          <div class="discount">скидка -36%</div>
          <div class="discount">акция -20%</div>
        </div>

        <div class="size-container">
          <select class="choose-size" name="" id="">
            <option value="null" selected disabled>Выбрать размер</option>
            <option value="24">Размер (см) 24</option>
            <option value="26">Размер (см)  26</option>
            <option value="28">Размер (см)  28</option>
            <option value="28">Размер (см)  30</option>
            <option value="28">Размер (см)  32</option>
            <option value="28">Размер (см)  34</option>
          </select>
          <a href="" class="standart-link">Определить размер</a>
        </div>

        <div class="buy-product">
          <div class="count-product">
            <button 
              class="mathematical-action" 
              @click="countProduct++">
                +
              </button>
            <p class="count">{{ countProduct }}</p>
            <button 
              class="mathematical-action" 
              @click="if(countProduct > 1) countProduct--;">
                –
              </button>
          </div>
          <div class="container-button">
            <button class="primary-button" @click="addToCart">Добавить в корзину</button>
            <button class="favorite-button" @click="addToCart"><img class="button-img" src="../assets/img/FavoriteLite.png" alt=""></button>
          </div>
        </div>
        <div class="link-container-border">
          <a href="" class="standart-link">Купить в 1 клик</a>
        </div>


        <div class="link-container">
          <a href="" class="standart-link"><img class="img-link" src="../assets/img/Clothes.png" alt="">Описание товара</a>
          <a href="" class="standart-link"><img class="img-link" src="../assets/img/Clock.png" alt="">Доставка и возврат</a>
          <a href="" class="standart-link"><img class="img-link" src="../assets/img/Pay.png" alt="">Способы оплаты</a>
        </div>
      </div>
    </div>

    <div class="link-style">
      <a href="#" class="standart-link">Посмотреть все стили</a>
    </div>
    
    <div class="container-photo">
      <img class="photo-big" src="../assets/img/ChildPhoto1.png" alt="">
      <div class="photo-tiles">
        <div class="photo-line">
          <img class="photo" src="../assets/img/ChildPhoto2.png" alt="">
          <div>
        
          </div>
          <img class="photo" src="../assets/img/ChildPhoto3.png" alt="">
        </div>
        <div class="photo-line">
          <img class="photo" src="../assets/img/ChildPhoto4.png" alt="">
          <img class="photo" src="../assets/img/ChildPhoto5.png" alt="">
        </div>
      </div>
    </div>
    <ModalWindow v-if="modalVisible" @close="modalVisible = false" :countProducts="countProducts" :name_products="nameProducts"/>
  </div>
</template>

<script>
import ModalWindow from '@/components/ModalWindow'

export default {
  data() {
    return {
      modalVisible: false,
      countProduct: 1,
      nameProduct: "Пижама для девочек",
      nameProducts: null,
      countProducts: null,
      arrFileNames: [
        {
          id: 1,
          fileNameMini: "MiniChild1",
          fileName: "Child1"
        },
        {
          id: 1,
          fileNameMini: "MiniChild2",
          fileName: "Child2"
        },
        {
          id: 1,
          fileNameMini: "MiniChild3",
          fileName: "Child3"
        },
        {
          id: 1,
          fileNameMini: "MiniChild4",
          fileName: "Child4"
        }
        ,{
          id: 1,
          fileNameMini: "MiniChild5",
          fileName: "Child5"
        }
      ],
      selectedFileName: "Child1"
    }
  },
  computed: {
    dynamicImg() {
      return require(`../assets/img/${this.selectedFileName}.png`)
    }
  },
  methods : { 
    ChangeImg(item) {
      this.selectedFileName = item.fileName
    },
    addToCart() {
      this.modalVisible = true
      this.nameProducts = this.nameProduct;
      this.countProducts = this.countProduct;
    }
  },
  components: {
    ModalWindow
  }
}
</script>

<style>

</style>