<template>
  <nav class="ui inverted grey attached segment index-navigation-mini">
    <div class="ui container">
      <div class="ui inverted grey secondary stackable menu">
        <h2 class="ui teal header item">管理</h2>
        <a href="/admin" class="nav-item item index-mobile" ><i class="home icon"></i>文章</a>
        <a href="/admin/types" class="nav-item item index-mobile" ><i class="th icon"></i>分类</a>
        <a href="/admin/albums" class="m-item item index-mobile"><i class="camera retro icon"></i>相册</a>
        <div class="right nav-item index-mobile menu">
          <div class="ui dropdown item">
            <div class="text">
              <img :src="avatar" alt="" class="ui avatar image">{{userName}}
            </div>
            <a @click="signOut()" class="item">注销</a>
          </div>
        </div>
      </div>

    </div>
  </nav>
</template>

<script>
    export default {
      name: "admin_navigate",
      data(){
        return{
          userName:localStorage.getItem('userName'),
          avatar:localStorage.getItem('avatar')
        }
      },
      methods: {
        signOut() {
          if (confirm('确定要注销吗?') == true) {
            localStorage.removeItem('token')
            localStorage.removeItem('githubLink')
            localStorage.setItem('userName','未登录')
            localStorage.setItem('avatar',"https://img95.699pic.com/xsj/10/tm/0h.jpg!/fw/700/watermark/url/L3hzai93YXRlcl9kZXRhaWwyLnBuZw/align/southeast")
            this.$router.go(0);
          }
        }
      },
      created() {

      }

    }
</script>

<style scoped>

</style>
