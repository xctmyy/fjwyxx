<template>
  <div class="anti-addiction-ad-container" v-if="isVisible">
    <div class="ad-content">
      <div class="ad-header">
        <h3 class="ad-title">反戒网瘾学校公益广告</h3>
        <button class="ad-close-btn" @click="closeAd">×</button>
      </div>
      <p class="ad-text">
        直到现在，仍有大量非法机构打着"戒网瘾"、"矫正孩子"的名义，行绑架、体罚、虐待之事，我们的孩子遭受了非人的对待。可能刚刚就有一个可怜的孩子遭受到了辱骂、殴打、性侵。
      </p>
      <div class="ad-actions">
        <button class="ad-btn-report" @click="reportToCyberSecurity">举报非法机构</button>
      </div>
    </div>
  </div>
</template>

<script setup lang="ts">
import { ref, onMounted } from 'vue';

// 控制广告是否可见的状态，默认设为true让广告持续显示
const isVisible = ref(true);

// 关闭广告
const closeAd = () => {
  isVisible.value = false;
  // 可以添加关闭后的处理逻辑，如保存到localStorage等
};

// 跳转到中央网信办举报网站
const reportToCyberSecurity = () => {
  window.open('https://www.12377.cn/', '_blank');
};

// 组件挂载时的处理
onMounted(() => {
  // 可以在这里添加初始化逻辑
});
</script>

<style scoped>
/* 主容器 - 固定在侧边并留出边距 */
.anti-addiction-ad-container {
  position: fixed;
  left: 20px; /* 与窗口左边界保持20px距离 */
  top: 50%;
  transform: translateY(-50%);
  z-index: 1000;
}

/* 广告内容容器 - 默认持续显示 */
.ad-content {
  background-color: white;
  width: 320px;
  border-radius: 0 10px 10px 0;
  box-shadow: 2px 2px 12px rgba(0, 0, 0, 0.15);
  border: 1px solid #ffccc7;
  animation: slideIn 0.5s ease-out;
}

/* 广告头部 - 包含标题和关闭按钮 */
.ad-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 15px 20px 0;
  margin-bottom: 10px;
}

/* 广告标题 */
.ad-title {
  color: #ff4d4f;
  font-size: 18px;
  margin: 0;
  font-weight: bold;
  flex: 1;
}

/* 关闭按钮 - X号样式 */
.ad-close-btn {
  background: none;
  border: none;
  font-size: 24px;
  color: #999;
  cursor: pointer;
  padding: 0;
  width: 30px;
  height: 30px;
  display: flex;
  align-items: center;
  justify-content: center;
  border-radius: 50%;
  transition: all 0.3s ease;
  margin-left: 10px;
}

.ad-close-btn:hover {
  background-color: #f0f0f0;
  color: #666;
  transform: scale(1.1);
}

/* 广告文本 */
.ad-text {
  color: #333;
  line-height: 1.6;
  margin-bottom: 20px;
  font-size: 14px;
  padding: 0 20px;
}

/* 操作按钮容器 */
.ad-actions {
  display: flex;
  justify-content: flex-end;
  padding: 0 20px 20px;
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

/* 滑入动画 - 从左侧滑入但考虑了边距 */
@keyframes slideIn {
  from {
    transform: translateX(-100%);
    opacity: 0;
  }
  to {
    transform: translateX(0);
    opacity: 1;
  }
}

/* 响应式设计 */
@media (max-width: 768px) {
  .ad-content {
    width: 280px;
  }
  
  .ad-title {
    font-size: 16px;
  }
  
  .ad-text {
    font-size: 13px;
  }
}

/* 添加一个轻微的呼吸动画，提高用户注意 */
.ad-content {
  animation: slideIn 0.5s ease-out, subtlePulse 4s infinite;
}

@keyframes subtlePulse {
  0% {
    transform: translateX(0) scale(1);
  }
  50% {
    transform: translateX(3px) scale(1.01);
  }
  100% {
    transform: translateX(0) scale(1);
  }
}
</style>