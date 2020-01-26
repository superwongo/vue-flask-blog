<template>
  <div class="vf-header">
    <div class="blog-header">
      <span class="pull-left">
        <a class="blog-title" href="/">VFBlog</a>
      </span>
<!--      <span class="toggle-menu pull-right">-->
<!--        <a class="menus-item"><i class="fa fa-bars fa-fw" aria-hidden="true"></i></a>-->
<!--      </span>-->
      <span class="pull-right">
        <el-menu class="menus-items" mode="horizontal" router background-color="rgba(0,0,0,0)">
          <el-menu-item class="menus-item" index="/"><i class="fa-fw fa fa-home"></i>首页</el-menu-item>
          <el-menu-item class="menus-item" index="/archives/"><i class="fa-fw fa fa-archive"></i>归档</el-menu-item>
          <el-menu-item class="menus-item" index="/tags/"><i class="fa-fw fa fa-tags"></i>标签</el-menu-item>
          <el-menu-item class="menus-item" index="/categories/"><i class="fa-fw fa fa-folder-open"></i>分类</el-menu-item>
          <el-menu-item class="menus-item" index="/about/"><i class="fa-fw fa fa-heart"></i>关于</el-menu-item>
        </el-menu>
      </span>
    </div>
  </div>
</template>

<script>
export default {
  name: 'vf-header'
}
</script>

<style lang="scss" scoped>
.vf-header {
  .blog-header {
    top: 0;
    z-index: 99;
    padding: 1rem 1.5rem;
    font-size: 18px;
    .pull-left {
      float: left;
      .blog-title {
        text-shadow: 0.1rem 0.1rem 0.2rem rgba(0,0,0,0.15);
        font-weight: bold;
        cursor: pointer;
        text-decoration: none;
        color: rgba(255,255,255,0.8);
      }
    }
    .pull-right {
      float: right;
    }
    .menus-items {
      border: none;
      .menus-item {
        i {
          color: #eeeeee;
        }
        padding: 0 0.4rem;
        color: #eeeeee;
        line-height: 2rem;
        height: 2rem;
        /*绝对定位*/
        position: relative;
        /*设置透明背景*/
        background-color: rgba(0,0,0,0) !important;
      }

      /*hover状态下展示底部横线*/
      .menus-item:after {
        /*相对定位*/
        position: absolute;
        content: "";
        /*设置横线位于menus_item元素底部*/
        bottom: -0.1rem;
        width: 100%;
        /*设置底部横线颜色、宽度等*/
        border-bottom: 0.1rem solid #409EFF;
        /*设置横线居中*/
        left: 50%;
        /*设置透明度为0*/
        opacity: 0;
        /*设置动画：先进后出*/
        transform: translate(-50%) scaleX(0);
        transition: .3s ease-in-out;
      }
      /*设置hover后样式*/
      .menus-item:hover::after {
        /*透明度为1,透明*/
        opacity: 1;
        transform: translate(-50%) scaleX(1);
      }
    }
  }
}
</style>
