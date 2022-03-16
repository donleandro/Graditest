<template>
  <div class="carousel">
    <div class="carouse--containerl">
      <img :src="featuredImage" class="carousel--featured-image"/>
    </div>
    <ul class="carousel-nav">
      <li v-for="(item, index) in images" :id="`product--image-${index}`" :key="index" :class="{'carousel-nav--button__select': featuredImage === item}"
          class="carousel-nav--button"
          @click="changeImage(index)">
        <img :src="item" class="carousel-nav--image"/>
      </li>
    </ul>
  </div>
</template>
<script>
export default {
  name: 'ProductCarousel',
  props: {
    images: {
      required: true
    },
    featured: {
      type: String,
      required: true
    }
  },
  created() {
    // this.featuredImage = this.featured;
    this.updateFeaturedImage();
  },
  data() {
    return {
      activeSlide: 0,
      featuredImage: ''
    }
  },
  methods: {
    nextSlide() {
      this.activeSlide = this.activeSlide + 1;
      this.updateFeaturedImage();
    },
    prevSlide() {
      this.activeSlide = this.activeSlide - 1;
      this.updateFeaturedImage();
    },
    changeImage(index) {
      this.activeSlide = index;
      this.updateFeaturedImage();
    },
    updateFeaturedImage() {
      this.featuredImage = this.images[this.activeSlide];
    }
  }
}
</script>
<style lang="scss" scoped>
.carousel {
  &-nav--button {
    cursor: pointer;
    display: inline-grid;
    width: 111px;
    /* height: 40px; */
    /* border: 1px solid #d5d5d5; */
    /* vertical-align: middle; */
    color: #d5d5d5;
    margin: 7px;

    &__select {
      border: 1px solid #d5d5d5;
    }
  }

  &-nav--image {
    width: 100%;
    height: 100%;
    object-fit: cover;
  }
}

.carousel--featured-image {
  width: 100%;
  object-fit: cover;
}

ul {
  list-style-type: none;
  margin: 0;
  padding: 0;
}
@media (max-width: 768px) {
  .carousel {
    &-nav--button {
      width: 16px;
      height: 16px;
      margin: 0 10px;
      border-radius: 50%;
      cursor: pointer;
      position: relative;
      background-color: white;
      border: 1px solid black;
      &__select {
        background-color: black;
      }
      img {
        display: none!important;
      }
    }
  }
}
</style>