<template>
  <div class="key-features-container">
    <div class="features-header">
      <div class="header-content">
        <h2 class="header-title">{{ config.header.title }}</h2>
        <p class="header-description">{{ config.header.description }}</p>
      </div>
      <a :href="config.header.learnMoreLink" class="learn-more">
        {{ config.header.learnMore }}
      </a>
    </div>
    <div class="features-grid">
      <div v-for="(feature, index) in config.features"
           :key="index"
           :class="['feature-card', `gradient-${index % 7}`]">
        <div class="feature-content">
          <h3 class="feature-title">{{ feature.title }}</h3>
          <p class="feature-description">{{ feature.description }}</p>
        </div>
        <div class="gradient-border"></div>
      </div>
    </div>
  </div>
</template>

<script setup>
defineProps({
  config: {
    type: Object,
    required: true
  }
})
</script>

<style scoped>
/* 添加新的样式 */
.features-header {
  display: flex;
  justify-content: space-between;
  align-items: center;
  margin-bottom: 3rem;
  padding: 0 2rem;
}

.header-content {
  flex: 1;
}

.header-title {
  font-size: 2.5rem;
  font-weight: bold;
  margin-bottom: 0.75rem;
  color: var(--vp-c-text-1);
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.1);
}

.header-description {
  font-size: 1.2rem;
  max-width: 900px;
  line-height: 1.6;
  color: var(--vp-c-text-1);
}

.learn-more {
  display: inline-block;
  padding: 0.8rem 1.6rem;
  background: white;
  color: #1a1a1a;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 500;
  transition: all 0.3s ease;
}

.learn-more:hover {
  transform: translateY(-2px);
  box-shadow: 0 4px 12px rgba(0, 0, 0, 0.1);
}

/* 保持原有的其他样式不变 */
.key-features-container {
  padding: 4rem 2rem;
  max-width: 1400px;
  margin: 0 auto;
  background: var(--vp-c-bg);
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(3, 1fr);
  gap: 2rem;
}

.feature-card {
  position: relative;
  border-radius: 16px;
  padding: 2rem;
  height: 280px;
  overflow: hidden;
  display: flex;
  flex-direction: column;
  transition: all 0.3s ease;
  background-size: 200% 200%;
  animation: gradientFlow 15s ease infinite;
  backdrop-filter: blur(10px);
}

.feature-content {
  z-index: 2;
  position: relative;
  height: 100%;
}

.feature-title {
  font-size: 1.8rem;
  font-weight: 600;
  margin-bottom: 1rem;
  color: rgba(255, 255, 255, 0.95);
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.2);
}

.feature-description {
  font-size: 1.1rem;
  line-height: 1.6;
  color: rgba(255, 255, 255, 0.8);
}

@keyframes gradientFlow {
  0% {
    background-position: 0% 0%, 100% 0%, 50% 0%, 0% 0%;
  }
  25% {
    background-position: 15% 15%, 85% 15%, 65% 15%, 15% 15%;
  }
  50% {
    background-position: 25% 25%, 75% 25%, 75% 25%, 25% 25%;
  }
  75% {
    background-position: 15% 85%, 85% 85%, 65% 85%, 15% 85%;
  }
  100% {
    background-position: 0% 0%, 100% 0%, 50% 0%, 0% 0%;
  }
}

/* 渐变背景系列 - 更鲜艳的颜色 */
.gradient-0 {
  background: 
    radial-gradient(circle at 0% 100%, rgba(255, 71, 71, 0.85) 0%, transparent 50%),
    radial-gradient(circle at 100% 100%, rgba(123, 97, 255, 0.85) 0%, transparent 50%),
    radial-gradient(circle at 50% 100%, rgba(255, 105, 180, 0.7) 0%, transparent 50%),
    linear-gradient(to top,
      rgba(18, 18, 18, 0.75) 0%,
      rgba(18, 18, 18, 0.9) 50%);
  background-size: 150% 150%;
  animation: gradientFlow 15s ease infinite;
}

.gradient-1 {
  background: 
    radial-gradient(circle at 0% 100%, rgba(72, 255, 0, 0.85) 0%, transparent 50%),
    radial-gradient(circle at 100% 100%, rgba(64, 166, 255, 0.85) 0%, transparent 50%),
    radial-gradient(circle at 50% 100%, rgba(255, 251, 0, 0.7) 0%, transparent 50%),
    linear-gradient(to top,
      rgba(18, 18, 18, 0.75) 0%,
      rgba(18, 18, 18, 0.9) 50%);
  background-size: 150% 150%;
  animation: gradientFlow 15s ease infinite;
}

.gradient-2 {
  background: 
    radial-gradient(circle at 0% 100%, rgba(255, 200, 110, 0.85) 0%, transparent 50%),
    radial-gradient(circle at 100% 100%, rgba(255, 71, 71, 0.85) 0%, transparent 50%),
    radial-gradient(circle at 50% 100%, rgba(140, 120, 255, 0.7) 0%, transparent 50%),
    linear-gradient(to top,
      rgba(18, 18, 18, 0.75) 0%,
      rgba(18, 18, 18, 0.9) 50%);
  background-size: 150% 150%;
  animation: gradientFlow 15s ease infinite;
}

.gradient-3 {
  background: 
    radial-gradient(circle at 0% 100%, rgba(0, 255, 255, 0.85) 0%, transparent 50%),
    radial-gradient(circle at 100% 100%, rgba(191, 64, 255, 0.85) 0%, transparent 50%),
    radial-gradient(circle at 50% 100%, rgba(255, 64, 255, 0.7) 0%, transparent 50%),
    linear-gradient(to top,
      rgba(18, 18, 18, 0.75) 0%,
      rgba(18, 18, 18, 0.9) 50%);
  background-size: 150% 150%;
  animation: gradientFlow 15s ease infinite;
}

.gradient-4 {
  background: 
    radial-gradient(circle at 0% 100%, rgba(140, 120, 255, 0.85) 0%, transparent 50%),
    radial-gradient(circle at 100% 100%, rgba(72, 255, 0, 0.85) 0%, transparent 50%),
    radial-gradient(circle at 50% 100%, rgba(110, 255, 220, 0.7) 0%, transparent 50%),
    linear-gradient(to top,
      rgba(18, 18, 18, 0.75) 0%,
      rgba(18, 18, 18, 0.9) 50%);
  background-size: 150% 150%;
  animation: gradientFlow 15s ease infinite;
}

.gradient-5 {
  background: 
    radial-gradient(circle at 0% 100%, rgba(255, 71, 71, 0.85) 0%, transparent 50%),
    radial-gradient(circle at 100% 100%, rgba(64, 166, 255, 0.85) 0%, transparent 50%),
    radial-gradient(circle at 50% 100%, rgba(255, 251, 0, 0.7) 0%, transparent 50%),
    linear-gradient(to top,
      rgba(18, 18, 18, 0.75) 0%,
      rgba(18, 18, 18, 0.9) 50%);
  background-size: 150% 150%;
  animation: gradientFlow 15s ease infinite;
}

.gradient-6 {
  background: 
    radial-gradient(circle at 0% 100%, rgba(110, 220, 255, 0.85) 0%, transparent 50%),
    radial-gradient(circle at 100% 100%, rgba(255, 71, 71, 0.85) 0%, transparent 50%),
    radial-gradient(circle at 50% 100%, rgba(255, 251, 0, 0.7) 0%, transparent 50%),
    linear-gradient(to top,
      rgba(18, 18, 18, 0.75) 0%,
      rgba(18, 18, 18, 0.9) 50%);
  background-size: 150% 150%;
  animation: gradientFlow 15s ease infinite;
}

/* 增强光晕效果 */
.feature-card::before {
  content: '';
  position: absolute;
  inset: 0;
  background: inherit;
  filter: blur(20px);
  opacity: 0.8;
  z-index: -1;
}

.feature-card::after {
  content: '';
  position: absolute;
  inset: 0;
  background: linear-gradient(
      to bottom,
      transparent,
      rgba(0, 0, 0, 0.2)
  );
  pointer-events: none;
}

.gradient-border {
  position: absolute;
  inset: 0;
  border-radius: 16px;
  padding: 1px;
  background: linear-gradient(
      45deg,
      rgba(255, 97, 210, 0.3),
      rgba(123, 97, 255, 0.3),
      rgba(97, 255, 206, 0.3),
      rgba(255, 97, 210, 0.3)
  );
  -webkit-mask: linear-gradient(#fff 0 0) content-box,
  linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor;
  mask-composite: exclude;
  opacity: 0;
  transition: opacity 0.3s ease;
}

.feature-card:hover {
  transform: translateY(-4px);
}

.feature-card:hover .gradient-border {
  opacity: 1;
}

@media (max-width: 1200px) {
  .features-grid {
    grid-template-columns: repeat(2, 1fr);
  }
}

@media (max-width: 768px) {
  .features-grid {
    grid-template-columns: 1fr;
  }

  .feature-card {
    height: 240px;
  }
}

@media (max-width: 768px) {
  .features-header {
    flex-direction: column;
    text-align: center;
    gap: 1.5rem;
  }

  .header-description {
    margin: 0 auto;
  }
}

/* 移动端适配 */
@media (max-width: 768px) {
  .header-title {
    font-size: 2rem;
  }

  .header-description {
    font-size: 1.1rem;
  }
}
</style> 
