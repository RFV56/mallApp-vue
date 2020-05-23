<template>
  <swiper>
      <swiper-item v-for="item in banner" :key="item.link">
          <a :href="item.link">
              <img :src="item.image">
          </a>
      </swiper-item>
  </swiper>
</template>

<script>
import Swiper from '@/components/common/swiper/Swiper'
import SwiperItem from '@/components/common/swiper/SwiperItem'
export default {
    name: 'HomeSwiper',
    components:{
        Swiper,
        SwiperItem
    },
    props:{
        banner: {
            type: Array,
            default(){
                return []
            }
        }
    }
}
</script>

<style>

</style>