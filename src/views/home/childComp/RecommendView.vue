<template>
  <div class="recommend">
    <div v-for="item in recommend" :key="item.link" class="recommend-item">
      <a :href="item.link">
        <img :src="item.image" />
        <div>{{item.title}}</div>
      </a>
    </div>
  </div>
</template>

<script>
export default {
  name: "RecommendView",
  props: {
    recommend: {
      type: Array,
      default() {
        return [];
      }
    }
  }
};
</script>

<style>
.recommend {
    display: flex;
    text-align: center;
    font-size: 16px;
    padding: 15px 0 25px;
    border-bottom: 8px solid #eee;
}
.recommend-item{
    flex: 1;
}

.recommend-item img{
    width: 70px;
    height: 70px;
    margin-bottom: 5px;
}
</style>