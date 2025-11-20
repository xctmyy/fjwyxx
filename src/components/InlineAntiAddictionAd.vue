<template>
  <div class="inline-ad-container">
    <div class="ad-banner">
      <div class="ad-warning-icon">⚠️</div>
      <div class="ad-content-wrapper">
        <h3 class="ad-title">反戒网瘾学校公益广告</h3>
        <p class="ad-text">
          直到现在，仍有大量非法机构打着"戒网瘾"、"矫正孩子"的名义，行绑架、体罚、虐待之事，我们的孩子遭受了非人的对待。可能刚刚就有一个可怜的孩子遭受到了辱骂、殴打、性侵。
        </p>
      </div>
    </div>
    <div class="ad-actions">
      <button class="ad-btn-report" @click="reportToCyberSecurity">举报非法机构</button>
    </div>
  </div>
</template>

<script setup lang="ts">
// 移除关闭功能，页面内广告无需关闭按钮

// 跳转到中央网信办举报网站
const reportToCyberSecurity = () => {
  window.open('https://www.12377.cn/', '_blank');
}
</script>

<style scoped>
/* 内联广告容器 */
.inline-ad-container {
  background-color: #fff5f5;
  border: 2px solid #ffccc7;
  border-radius: 8px;
  margin: 20px 0;
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.05);
  transition: all 0.3s ease;
  overflow: hidden;
}

/* 广告横幅部分 */
.ad-banner {
  display: flex;
  align-items: flex-start;
  padding: 16px;
  animation: fadeIn 0.5s ease-in;
}

/* 警告图标 */
.ad-warning-icon {
  font-size: 28px;
  margin-right: 16px;
  flex-shrink: 0;
  animation: pulse 2s infinite;
}

/* 内容包装器 */
.ad-content-wrapper {
  flex: 1;
}

/* 广告标题 */
.ad-title {
  color: #ff4d4f;
  font-size: 18px;
  margin: 0 0 8px 0;
  font-weight: bold;
}

/* 广告文本 */
.ad-text {
  color: #333;
  line-height: 1.6;
  margin: 0;
  font-size: 14px;
}

/* 操作按钮区域 */
.ad-actions {
  background-color: #fff0f0;
  padding: 12px 16px;
  border-top: 1px solid #ffccc7;
  display: flex;
  justify-content: flex-end;
}

/* 举报按钮 */
.ad-btn-report {
  background-color: #ff4d4f;
  color: white;
  border: none;
  padding: 8px 16px;
  border-radius: 4px;
  cursor: pointer;
  font-size: 14px;
  transition: background-color 0.3s ease;
}

.ad-btn-report:hover {
  background-color: #d32f2f;
}

/* 淡入动画 */
@keyframes fadeIn {
  from {
    opacity: 0;
    transform: translateY(10px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

/* 脉冲动画 */
@keyframes pulse {
  0% {
    transform: scale(1);
  }
  50% {
    transform: scale(1.1);
  }
  100% {
    transform: scale(1);
  }
}

/* 响应式设计 */
@media (max-width: 768px) {
  .ad-banner {
    padding: 12px;
  }
  
  .ad-warning-icon {
    font-size: 24px;
    margin-right: 12px;
  }
  
  .ad-title {
    font-size: 16px;
  }
  
  .ad-text {
    font-size: 13px;
  }
  
  .ad-actions {
    padding: 10px 12px;
  }
}

/* 悬停效果 */
.inline-ad-container:hover {
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
  transform: translateY(-2px);
}
</style>