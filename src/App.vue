<script setup>
import RightList from '@/components/rightList/RightList.vue'
import LeftList from '@/components/leftList/LeftList.vue'


</script>

<template>
  <div class="container container__list">
    <LeftList></LeftList>
    <RightList></RightList>
  </div>
</template>

<style lang="scss">
.container__list {
  width: 100%;
  display: flex;
  align-items: center;
  justify-content: space-between;
  gap: 20px;
  margin-top: 20px;
}
</style>
