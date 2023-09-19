<template>
  <div class="table-column">
    <span class="table-column__title" v-if="columnTitle">{{columnTitle}}:</span>
    <slot v-if="!img"></slot>
    <img v-else class="table-column-image" :src="srcImg"/>
  </div>
</template>

<script setup>
const props = defineProps({
  img: {
    type: Boolean
  },
  srcImg: {
    type: String
  },
  columnTitle: {
    type: String
  },
})
</script>


<style lang="scss" scoped>
.table-column {
  padding: 15px 0;
  position: relative;
  &-image {
    max-width: 100%;
    @media screen and (max-width: 860px) {
      max-width: 200px;
    }
  }
  &__title {
    margin-right: 5px;
    display: none;
    @media screen and (max-width: 860px) {
      display: inline-block;
    }
  }
}
</style>