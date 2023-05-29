<template>
  <div>
    <footer class="ui footer vertical segment index-footer-big">
      <div class="ui center aligned container">
        <div class="ui inverted grey divided stackable">
          <p class="ui text index-text-lined index-text-thin index-text-spaced">联系我:1739716491@qq.com</p>
          <p class="ui text index-text-lined index-text-thin index-text-spaced">Copyright ©2021-2022 axiV548</p>
          博客已稳定运行：{{ runningDays }}
          <br>
        </div>
      </div>
    </footer>
  </div>
</template>

<script>
export default {
  data() {
    return {
      startDate: new Date('2021-01-01T00:00:00'), // 替换为你的博客开始日期和时间
      runningDays:'',
    }
  },
  methods: {
    blogRunningDays() {
      const startTime = this.startDate.getTime();
      const currentTime = new Date().getTime();
      const timeDiff = currentTime - startTime;

      // 计算时分秒
      const seconds = Math.floor(timeDiff / 1000) % 60;
      const minutes = Math.floor(timeDiff / (1000 * 60)) % 60;
      const hours = Math.floor(timeDiff / (1000 * 60 * 60)) % 24;
      const days = Math.floor(timeDiff / (1000 * 60 * 60 * 24));

      this.runningDays = `${days} 天 ${hours} 小时 ${minutes} 分钟 ${seconds} 秒`;
    },
  },
  created() {
    // 初始化运行时间
    this.blogRunningDays()
    // 每秒更新一次运行时间
    setInterval(() => {
      this.blogRunningDays();
    }, 1000);
  },
  name: "footer"
}


</script>

<style scoped>

</style>
