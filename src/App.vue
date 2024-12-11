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
      <div class="vertical-text">兔兔一起強大</div>

      <router-view v-slot="{ Component }">
        <keep-alive include="index">
          <component :is="Component"></component>
        </keep-alive>
      </router-view>
    </v-main>
  </v-app>
</template>

<style scoped>
.background {
  display: flex;
  background-color: #eceff3;
  background-image: url(./assets/466117278_948320513849764_6602088881986865474_png.png); /* 替換成你的圖片路徑 */
  background-size: cover; /* 讓圖片完整顯示 */
  background-position: top; /* 背景居中顯示 */
  background-repeat: no-repeat; /* 防止圖片重複 */
  height: 1500px; /* 高度設置為視口高度，保證背景圖片完全顯示 */
}

.vertical-text {
  writing-mode: vertical-rl; /* 垂直文字排列 */
  text-orientation: upright; /* 保持文字直立顯示 */
  font-size: 200px;
  position: absolute;
  right: 20px; /* 調整到右側 */ /* 垂直居中 */
  transform: translateY(-50%); /* 修正垂直居中的偏移 */
  color: #333; /* 調整文字顏色 */
  margin-top: 500px;
  color: rgb(240, 240, 240);
  font-style: inherit;
  z-index: 0;
}
</style>
