<template>
  <div class="dashboard-container">
     <el-card>
         <p>UI组件库</p>
          <hr>
         <div>
            分为两部分实现：<br>
            1.整体布局：
            <ul>
              <li>全局固定路由和异步路由结合</li>
              <li>根据路由表动态生成左侧菜单栏</li>
              <li>用户角色和路由匹配实现权限控制</li>
              <li>全局皮肤设置</li>
              <li>全局按钮设置</li>
              <li>全局字体大小设置</li>
            </ul>
            2.组件部分：
            <ul>
              <li>table部分：可搜索table，动态增加删除行table，树形table，自定义单元格</li>
              <li>表单：下拉，单选 ，多选，文本域等</li>
              <li>icons</li>
              <li>charts</li>
              <li>树形控件</li>
              <li>可拓展部分</li>
            </ul>
         </div>
     </el-card>
  </div>
</template>

<script>
export default {
  name: 'Dashboard'
}
</script>

<style lang="scss" scoped>
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
