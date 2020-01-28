<template>
  <div class="vf-aside">
    <span class="aside-card">
      <el-card :body-style="{ padding: 0 }" shadow="hover">
        <author-total-info show-username/>
      </el-card>
    </span>
  </div>
</template>

<script>
import authorTotalInfo from '@/components/author-total-info'

export default {
  name: 'vf-aside',
  components: {
    authorTotalInfo
  }
}
</script>

<style lang="scss" scoped>
.vf-aside {
  .aside-card {
    display: flex;
    align-items: center;
    .el-card {
      margin-top: 2rem;
      margin-left: 0.5rem;
      width: 90%;
    }
  }
}
</style>
