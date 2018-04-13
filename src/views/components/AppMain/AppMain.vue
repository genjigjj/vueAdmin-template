<template>
  <div class="dashboard-container">
 <!--   <div class="dashboard-text">name:{{name}}</div>
    <div class="dashboard-text">roles:<span v-for='role in roles' :key='role'>{{role}}</span></div>-->
    <el-pagination
      :current-page.sync="currentPage"
      background
      layout="total,sizes, prev, pager, next"
      :page-count="total"
      :total="total">
    </el-pagination>
    <div>{{currentPage}}</div>
    <div>
      <router-link :to="{name:'Test'}">跳转</router-link>
    </div>
  </div>
</template>

<script>
import { mapGetters } from 'vuex'
export default {
  name: 'dashboard',
  computed: {
    ...mapGetters([
      'name',
      'roles'
    ])
  },
  data() {
    return {
      currentPage: 1,
      total: 100
    }
  },
  methods: {
  }
}
</script>

<style rel="stylesheet/scss" lang="scss" scoped>
.dashboard {
  &-container {
    margin: 30px;
  }
  &-text {
    font-size: 30px;
    line-height: 46px;
  }
}
</style>
