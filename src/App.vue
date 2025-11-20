<script setup lang="ts">
// 导入反戒网瘾学校公益广告组件
import AntiInternetAddictionAd from './components/AntiInternetAddictionAd.vue'
// 导入页面内反戒网瘾学校公益广告组件
import InlineAntiAddictionAd from './components/InlineAntiAddictionAd.vue'
// 导入页眉反戒网瘾学校公益广告组件
import HeaderAntiAddictionAd from './components/HeaderAntiAddictionAd.vue'
// 导入页脚反戒网瘾学校公益广告组件
import FooterAntiAddictionAd from './components/FooterAntiAddictionAd.vue'
</script>

<template>
  <div class="app-container">
    <!-- 页眉广告组件 -->
    <HeaderAntiAddictionAd />
    
    <div class="content-wrapper">
      <AntiInternetAddictionAd />
      <div class="main-content">
      <h1>XCUI 测试页面</h1>
      <p>这是一个Vue自建UI库的测试页面，侧边默认显示了反戒网瘾学校公益广告组件。</p>
      <p>点击右上角的 × 按钮可以关闭侧边广告。</p>
      
      <!-- 第一部分内容 -->
      <div class="content-section">
        <h2>内容第一部分</h2>
        <p>这里是页面的第一部分内容。在实际应用中，这里可能包含文章正文、产品介绍或其他重要信息。</p>
        <p>我们致力于为用户提供更好的使用体验，同时也关注社会公益事业。</p>
      </div>
      
      <!-- 页面内广告组件 - 插入在内容之间 -->
      <InlineAntiAddictionAd />
      
      <!-- 第二部分内容 -->
      <div class="content-section">
        <h2>内容第二部分</h2>
        <p>这里是页面的第二部分内容。页面内广告被合理地插入到内容之间，既保证了用户体验，又能有效传达公益信息。</p>
        <p>感谢您对公益事业的支持。</p>
      </div>
    </div>
    </div>
    
    <!-- 页脚广告组件 -->
    <FooterAntiAddictionAd />
  </div>
</template>

<style>
/* 全局重置 */
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}

body {
  font-family:
    -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, 'Helvetica Neue', Arial, sans-serif;
  line-height: 1.6;
  color: #333;
}
</style>

<style scoped>
.app-container {
  min-height: 100vh;
  display: flex;
  flex-direction: column;
  position: relative;
}

.content-wrapper {
  flex: 1;
  display: flex;
  justify-content: center;
  align-items: flex-start;
  padding: 40px 20px;
  width: 100%;
}

.main-content {
  text-align: center;
  max-width: 800px;
  width: 100%;
  padding: 20px;
}

h1 {
  color: #1890ff;
  margin-bottom: 20px;
  font-size: 2.5rem;
}

h2 {
  color: #52c41a;
  margin: 30px 0 20px;
  font-size: 1.8rem;
}

p {
  margin-bottom: 15px;
  font-size: 1.1rem;
  line-height: 1.7;
}

.content-section {
  margin: 30px 0;
  padding: 20px;
  background-color: #fafafa;
  border-radius: 8px;
  border: 1px solid #f0f0f0;
  transition: all 0.3s ease;
}

.content-section:hover {
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.08);
}

/* 响应式设计 */
@media (max-width: 768px) {
  .app-container {
    padding: 20px 15px;
  }
  
  h1 {
    font-size: 2rem;
  }
  
  h2 {
    font-size: 1.5rem;
  }
  
  p {
    font-size: 1rem;
  }
}
</style>
