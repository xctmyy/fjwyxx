<template>
  <div v-if="isVisible" class="footer-ad-container">
    <div class="footer-ad-content">
      <div class="footer-ad-warning-icon">⚠️</div>
      <div class="footer-ad-text-container">
        <h3 class="footer-ad-title">反戒网瘾学校公益宣传</h3>
        <p class="footer-ad-description">关注青少年心理健康，拒绝暴力教育，共建和谐社会。如有需求，请联系专业心理辅导机构。</p>
      </div>
      <button class="footer-ad-action-btn" @click="reportToCyberSecurity">中央网信办举报</button>
      <button class="footer-ad-close-btn" @click="closeAd" aria-label="关闭广告">×</button>
    </div>
  </div>
</template>

<script setup lang="ts">
// 页脚反戒网瘾学校公益广告组件
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
.footer-ad-container {
  background: linear-gradient(90deg, #c0392b, #e74c3c);
  color: white;
  padding: 20px 0;
  width: 100%;
  box-shadow: 0 -2px 10px rgba(231, 76, 60, 0.3);
  animation: footerAdSlideUp 0.6s ease-out;
  margin-top: 40px;
  position: relative;
}

.footer-ad-content {
  display: flex;
  align-items: center;
  max-width: 1200px;
  margin: 0 auto;
  padding: 0 20px;
  flex-wrap: wrap;
  gap: 20px;
}

.footer-ad-warning-icon {
  font-size: 32px;
  flex-shrink: 0;
  animation: footerAdPulse 2s infinite;
}

.footer-ad-text-container {
  flex: 1;
  min-width: 280px;
}

.footer-ad-title {
  margin: 0 0 8px 0;
  font-size: 18px;
  font-weight: 600;
  letter-spacing: 0.5px;
}

.footer-ad-description {
  margin: 0;
  font-size: 14px;
  opacity: 0.9;
  line-height: 1.6;
}

.footer-ad-action-btn {
  background-color: rgba(255, 255, 255, 0.2);
  color: white;
  border: 1px solid rgba(255, 255, 255, 0.3);
  padding: 10px 20px;
  border-radius: 25px;
  font-size: 15px;
  font-weight: 500;
  text-decoration: none;
  transition: all 0.3s ease;
  flex-shrink: 0;
}

.footer-ad-action-btn:hover {
  background-color: white;
  color: #e74c3c;
  transform: translateY(-2px);
  box-shadow: 0 6px 12px rgba(0, 0, 0, 0.2);
}

.footer-ad-close-btn {
  position: absolute;
  top: 12px;
  right: 20px;
  width: 28px;
  height: 28px;
  border: none;
  background-color: rgba(255, 255, 255, 0.2);
  color: white;
  border-radius: 50%;
  font-size: 18px;
  font-weight: bold;
  cursor: pointer;
  display: flex;
  align-items: center;
  justify-content: center;
  transition: all 0.3s ease;
  line-height: 1;
}

.footer-ad-close-btn:hover {
  background-color: rgba(255, 255, 255, 0.4);
  transform: scale(1.1);
}

/* 动画效果 */
@keyframes footerAdSlideUp {
  from {
    transform: translateY(100%);
    opacity: 0;
  }
  to {
    transform: translateY(0);
    opacity: 1;
  }
}

@keyframes footerAdPulse {
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
  .footer-ad-container {
    padding: 15px 0;
  }
  
  .footer-ad-content {
    padding: 0 15px;
    gap: 15px;
  }
  
  .footer-ad-warning-icon {
    font-size: 28px;
  }
  
  .footer-ad-title {
    font-size: 17px;
  }
  
  .footer-ad-description {
    font-size: 13px;
  }
  
  .footer-ad-action-btn {
    padding: 8px 16px;
    font-size: 14px;
  }
}

@media (max-width: 480px) {
  .footer-ad-content {
    flex-direction: column;
    text-align: center;
    gap: 12px;
    padding-right: 45px; /* 为关闭按钮留出空间 */
  }
  
  .footer-ad-text-container {
    min-width: auto;
  }
  
  .footer-ad-warning-icon {
    font-size: 24px;
  }
  
  .footer-ad-title {
    font-size: 16px;
  }
  
  .footer-ad-close-btn {
    top: 8px;
    right: 12px;
    width: 24px;
    height: 24px;
    font-size: 16px;
  }
}
</style>