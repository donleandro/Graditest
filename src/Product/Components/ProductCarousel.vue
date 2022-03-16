<template>
  <div class="carousel">
    <div class="carouse--containerl">
      <img :src="featuredImage" class="carousel--featured-image"/>
    </div>
    <div class="carousel-nav">
      <button v-for="(item, index) in images" :id="`product--image-${index}`" :key="index" class="carousel-nav--button"
              @click="changeImage(index)">
      </button>
    </div>
  </div>
</template>
<script>
export default {
  name: 'ProductCarousel',
  props: {
    images: {
      required: true
    },
    featured:{
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