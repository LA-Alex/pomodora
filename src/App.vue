<template>
  <v-app>
    <v-app-bar>
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
  background-image: url(./assets/466117278_948320513849764_6602088881986865474_png.png); /* 替換成你的圖片路徑 */
  background-size: cover; /* 背景覆蓋整個區域 */
  background-position: center; /* 背景居中顯示 */
  background-repeat: no-repeat; /* 防止圖片重複 */
  height: 100vh; /* 確保背景覆蓋整個頁面 */
}
</style>
