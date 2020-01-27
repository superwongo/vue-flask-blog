<template>
  <div class="vf-header">
    <div class="blog-header">
      <span class="pull-left">
        <a class="blog-title" href="/">VFBlog</a>
      </span>
      <span class="toggle-menu pull-right" @click="toggleMenu">
        <a class="menus-item"><i class="fa fa-bars fa-fw" aria-hidden="true"></i></a>
      </span>
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
    <el-drawer :visible.sync="drawer" :with-header="false" size="40%" class="mobile-sidebar">
<!--      <div id="mobile-menu-mask"></div>-->
      <div class="mobile-sidebar-menus">
        <div class="mobile-author-icon">
          <img class="avatar-img" src="../assets/images/avatar.png" onerror="onerror=null;src='../assets/images/friend_404.gif'" alt="avatar">
        </div>
        <div class="mobile-post-data">
          <div class="mobile-data-item">
            <router-link to="/archives/" class="mobile-data-link">
              <div class="headline">文章</div><div class="length-num">2</div>
            </router-link>
          </div>
          <div class="mobile-data-item">
            <router-link to="/tags/" class="mobile-data-link">
              <div class="headline">标签</div><div class="length-num">2</div>
            </router-link>
          </div>
          <div class="mobile-data-item">
            <router-link to="/categories/" class="mobile-data-link">
              <div class="headline">分类</div><div class="length-num">4</div>
            </router-link>
          </div>
        </div>
        <hr>
        <el-menu class="mobile-menus-items" router background-color="rgba(0,0,0,0)">
          <el-menu-item class="mobile-menus-item" index="/">
            <i class="fa-fw fa fa-home"></i><span slot="title">首页</span>
          </el-menu-item>
          <el-menu-item class="mobile-menus-item" index="/archives/">
            <i class="fa-fw fa fa-archive"></i><span slot="title">归档</span>
          </el-menu-item>
          <el-menu-item class="mobile-menus-item" index="/tags/">
            <i class="fa-fw fa fa-tags"></i><span slot="title">标签</span>
          </el-menu-item>
          <el-menu-item class="mobile-menus-item" index="/categories/">
            <i class="fa-fw fa fa-folder-open"></i><span slot="title">分类</span>
          </el-menu-item>
          <el-menu-item class="mobile-menus-item" index="/about/">
            <i class="fa-fw fa fa-heart"></i><span slot="title">关于</span>
          </el-menu-item>
        </el-menu>
      </div>
    </el-drawer>
  </div>
</template>

<script>
export default {
  name: 'vf-header',
  data() {
    return {
      drawer: false,
    }
  },
  methods: {
    toggleMenu: function () {
      this.drawer = true
    }
  }
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
    .toggle-menu, .menus-items {
      border: none;
      .menus-item {
        i {
          color: #eeeeee;
        }

        padding: 0 0.4rem;
        color: #eeeeee;
        line-height: 2rem;
        height: 2rem;
      }
    }
    .menus-items {
      .menus-item {
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
  .mobile-sidebar {
    .mobile-sidebar-menus {
      .mobile-author-icon {
        padding: 1rem 1.5rem;
        text-align: center;
        .avatar-img {
          /*display: inline-block;*/
          width: 6rem;
          height: 6rem;
          border-radius: 3rem;
          /*vertical-align: top;*/
          /*transition: all 0.3s;*/
        }
      }
      .mobile-post-data {
        display: flex;
        justify-content: center;
        padding: 0.5rem 1rem;
        .mobile-data-item {
          flex: 1;
          .mobile-data-link {
            text-decoration: none;
            text-align: center;
            cursor: pointer;
            .headline {
              /*display: block;*/
              color: #4c4948;
              text-transform: uppercase;
              font-size: 0.8rem;
              padding-bottom: 0.5rem;
            }
            .length-num {
              color: #000000;
              font-size: 1rem;
            }
          }
        }
      }
      .mobile-menus-items {
        /*border: none;*/
        .mobile-menus-item {
          i {
            color: #4c4948;
            padding-left: 1.5rem;
            padding-right: 2rem;
          }
          font-size: 1rem;
          padding: 0 0.3rem;
          color: #4c4948;
          line-height: 2rem;
          height: 2rem;
          /*绝对定位*/
          position: relative;
          /*设置透明背景*/
          background-color: rgba(0,0,0,0) !important;
        }
      }
      hr {
        position: relative;
        margin: 2rem auto;
        width: calc(100% - 4px);
        border: 2px dashed #a4d8fa;
        background: #fff;
      }
      hr:hover:before {
        left: calc(95% - 20px);
      }
      hr:before {
        position: absolute;
        top: -10px;
        left: 5%;
        z-index: 1;
        color: #49b1f5;
        content: '\f0c4';
        font: normal normal normal 14px/1 FontAwesome;
        font-size: 20px;
        transition: all 1s ease-in-out;
      }
    }
  }
}
</style>
