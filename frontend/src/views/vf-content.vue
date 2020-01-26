<template>
  <div class="vf-content">
    <nav class="full-page">
      <div class="site-info">
        <div class="site-title">
          <span class="blog-title">VFBlog</span>
        </div>
        <div class="site-sub-title">
          <span class="sub-title"></span>
        </div>
        <div class="site-social-icons">
          <a class="social-icon" href="https://github.com/superwongo" target="_blank">
            <i class="fa fa-github" aria-hidden="true"></i>
          </a>
          <a class="social-icon" href="mailto:wangchao_198912@126.com" target="_blank">
            <i class="fa fa-envelope" aria-hidden="true"></i>
          </a>
        </div>
      </div>
      <div class="scroll-down"><i class="fa fa-angle-down scroll-down-effects"></i></div>
    </nav>
  </div>
</template>

<script>
import Typed from 'typed.js'

export default {
  name: 'vf-content',
  mounted() {
    new Typed(".sub-title", {
      strings: '今日事&#44;今日毕,Never put off till tomorrow what you can do today'.split(","),
      startDelay: 300,
      typeSpeed: 100,
      loop: true,
      backSpeed: 50
    });
  }
}
</script>

<style lang="scss" scoped>
.vf-content {
  /*position: relative;*/
  /*margin-bottom: 1rem;*/
  /*width: 100%;*/
  .full-page {
    display: flex;
    justify-content: center;
    align-items: center;
    height: 80vh;
    /*#site-info {*/
    /*  position: absolute;*/
    /*  width: 100%;*/
    /*}*/
    .site-info,
    .site-sub-title {
      color: #eee;
      text-align: center;
      text-shadow: 0.1rem 0.1rem 0.2rem rgba(0,0,0,0.15);
      line-height: 1.5;
    }
    .site-title {
      font-weight: bold;
      font-size: 2rem;
    }
    .site-sub-title {
      font-size: 1rem;
    }
    .site-social-icons .social-icon {
      margin: 0 0.5rem;
      color: #eee;
      text-shadow: 0.1rem 0.1rem 0.2rem rgba(0,0,0,0.15);
      font-size: 0.9rem;
      cursor: pointer;
    }
    .scroll-down {
      position: absolute;
      bottom: 0;
      width: 100%;
      height: 3rem;
      text-align: center;
      font-size: 30px;
      cursor: pointer;
    }
    .scroll-down .scroll-down-effects {
      position: absolute;
      color: #fff;
    }
    .scroll-down-effects {
      animation: scroll-down-effect 1.5s infinite;
    }
    @keyframes scroll-down-effect {
      0% {
        top: 0;
        opacity: 0.4;
        -ms-filter: "progid:DXImageTransform.Microsoft.Alpha(Opacity=40)";
        filter: alpha(opacity=40);
      }
      50% {
        top: -16px;
        opacity: 1;
        -ms-filter: none;
        filter: none;
      }
      100% {
        top: 0;
        opacity: 0.4;
        -ms-filter: "progid:DXImageTransform.Microsoft.Alpha(Opacity=40)";
        filter: alpha(opacity=40);
      }
    }
  }
}
</style>
