<template>
  <transition name="fade" mode="out-in">
    <div :key="index">
      <gallery
        :mainSrc="galleries[index].mainSrc"
        :commentTitle="galleries[index].commentTitle"
        :commentIrai="galleries[index].commentIrai"
        :commentDesign="galleries[index].commentDesign"
        :subImages="galleries[index].subImages"
      ></gallery>
    </div>
  </transition>
</template>
<script>
import Gallery from "../components/gallery.vue";
import { galleriesTemplate } from "../assets/gallery";
export default {
  components: {
    Gallery
  },
  data() {
    return {
      index: 0,
      galleries: galleriesTemplate
    };
  }
};
</script>
<style lang="scss" scoped>
.fade-enter-active,
.fade-leave-active {
  transition: opacity 2s;
}
.fade-enter, .fade-leave-to /* .fade-leave-active below version 2.1.8 */ {
  opacity: 0;
}
</style>
