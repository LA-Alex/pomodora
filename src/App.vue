<template>
  <v-app>
    <v-app-bar :style="{ backgroundColor: '#fbd71f' }">
      <v-container class="d-flex align-center">
        <v-app-bar-title>番茄鐘</v-app-bar-title>
        <v-btn prepend-icon="mdi-home" to="/">首頁</v-btn>
        <v-btn prepend-icon="mdi-format-list-bulleted" to="/list">事項</v-btn>
        <v-btn prepend-icon="mdi-cog" to="/settings">設定</v-btn>
      </v-container>
    </v-app-bar>
    <v-main class="background">
      <!--
        slot = 插槽 = 自訂元件內的某部分 HTML
        v-slot="元件插槽提供的可用變數"
        Component = 目前路由應該顯示的元件
      -->
      <router-view v-slot="{ Component }">
        <!--
          keep-alive 包住的元件不會被銷毀
          include 指定保留的元件
        -->
        <keep-alive include="index">
          <component :is="Component"></component>
        </keep-alive>
      </router-view>
    </v-main>
  </v-app>
</template>

<style scoped>
.background {
  background-color: #eceff3;
  background-image: url(./assets/466117278_948320513849764_6602088881986865474_png.png); /* 替換成你的圖片路徑 */
  background-size: cover; /* 讓圖片完整顯示 */
  background-position: top; /* 背景居中顯示 */
  background-repeat: no-repeat; /* 防止圖片重複 */
  height: 1500px; /* 高度設置為視口高度，保證背景圖片完全顯示 */
  /* 宽度设置为100% */
}
</style>
