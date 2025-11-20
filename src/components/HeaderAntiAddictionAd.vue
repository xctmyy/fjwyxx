<template>
  <div v-if="isVisible" class="header-ad-container">
    <div class="header-ad-content">
      <div class="header-ad-warning-icon">⚠️</div>
      <div class="header-ad-text-container">
        <h3 class="header-ad-title">救救孩子</h3>
        <p class="header-ad-description">
          直到现在，仍有大量青少年被关在非法的戒网瘾学校中，遭受虐待、殴打、性侵
        </p>
      </div>
      <button class="header-ad-action-btn" @click="reportToCyberSecurity">中央网信办举报</button>
      <button class="header-ad-close-btn" @click="closeAd" aria-label="关闭广告">×</button>
    </div>
  </div>
</template>

<script setup lang="ts">
// 页眉反戒网瘾学校公益广告组件
import { ref } from 'vue'

// 控制广告显示状态
const isVisible = ref(true)

// 关闭广告方法
const closeAd = () => {
  isVisible.value = false
}

// 跳转到中央网信办举报网站
const reportToCyberSecurity = () => {
  window.open('https://www.12377.cn/', '_blank')
}
</script>

<style scoped>
.header-ad-container {
  background: linear-gradient(90deg, #e74c3c, #c0392b);
  color: white;
  padding: 12px 0;
  width: 100%;
  box-shadow: 0 2px 10px rgba(231, 76, 60, 0.3);
  animation: headerAdSlideDown 0.6s ease-out;
  position: sticky;
  top: 0;
  z-index: 1000;
  position: relative;
}

.header-ad-content {
  display: flex;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  flex-wrap: wrap;
  gap: 16px;
}

.header-ad-warning-icon {
  font-size: 24px;
  flex-shrink: 0;
  animation: headerAdPulse 2s infinite;
}

.header-ad-text-container {
  flex: 1;
  min-width: 250px;
}

.header-ad-title {
  margin: 0 0 4px 0;
  font-size: 16px;
  font-weight: 600;
  letter-spacing: 0.5px;
}

.header-ad-description {
  margin: 0;
  font-size: 14px;
  opacity: 0.9;
  line-height: 1.4;
}

.header-ad-action-btn {
  background-color: rgba(255, 255, 255, 0.2);
  color: white;
  border: 1px solid rgba(255, 255, 255, 0.3);
  padding: 6px 16px;
  border-radius: 20px;
  font-size: 14px;
  font-weight: 500;
  text-decoration: none;
  transition: all 0.3s ease;
  flex-shrink: 0;
}

.header-ad-action-btn:hover {
  background-color: white;
  color: #e74c3c;
  transform: translateY(-1px);
  box-shadow: 0 4px 8px rgba(0, 0, 0, 0.2);
}

.header-ad-close-btn {
  position: absolute;
  top: 8px;
  right: 16px;
  width: 24px;
  height: 24px;
  border: none;
  background-color: rgba(255, 255, 255, 0.2);
  color: white;
  border-radius: 50%;
  font-size: 16px;
  font-weight: bold;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
  line-height: 1;
}

.header-ad-close-btn:hover {
  background-color: rgba(255, 255, 255, 0.4);
  transform: scale(1.1);
}

/* 动画效果 */
@keyframes headerAdSlideDown {
  from {
    transform: translateY(-100%);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

@keyframes headerAdPulse {
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
  .header-ad-container {
    padding: 10px 0;
  }

  .header-ad-content {
    padding: 0 15px;
    gap: 12px;
  }

  .header-ad-warning-icon {
    font-size: 20px;
  }

  .header-ad-title {
    font-size: 15px;
  }

  .header-ad-description {
    font-size: 13px;
  }

  .header-ad-action-btn {
    padding: 5px 12px;
    font-size: 13px;
  }
}

@media (max-width: 480px) {
  .header-ad-content {
    flex-direction: column;
    text-align: center;
    gap: 10px;
    padding-right: 40px; /* 为关闭按钮留出空间 */
  }

  .header-ad-text-container {
    min-width: auto;
  }

  .header-ad-close-btn {
    top: 5px;
    right: 10px;
    width: 20px;
    height: 20px;
    font-size: 14px;
  }
}
</style>
