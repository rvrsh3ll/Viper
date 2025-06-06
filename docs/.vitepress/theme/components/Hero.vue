<template>
  <div class="hero-container">
    <div class="hero-section gradient-hero">
      <div class="main">
        <div class="content">
          <div class="text">
            <h1 class="name">{{ config.name }}</h1>
            <p class="tagline">{{ config.tagline }}</p>
            <div class="actions">
              <a class="action theme-brand" :href="config.actions[0].link">
                <svg class="docker-icon" viewBox="0 0 1024 1024" version="1.1" xmlns="http://www.w3.org/2000/svg">
                  <path d="M1004.544 466.08a161.504 161.504 0 0 0-119.52-10.816 158.88 158.88 0 0 0-64.608-101.216l-12.8-10.08-10.848 12.16a133.888 133.888 0 0 0-25.28 96.32 123.552 123.552 0 0 0 24.128 64.704 187.648 187.648 0 0 1-34.752 15.296A232.416 232.416 0 0 1 689.216 544H13.568l-1.44 15.136a282.656 282.656 0 0 0 23.776 147.2l9.248 18.336 1.056 1.728c63.52 104.896 190.24 159.232 311.808 159.232 235.392 0 414.368-112.352 503.552-328.224 59.584 3.04 120.544-14.112 149.696-69.408l7.424-14.112-14.144-7.936z" fill="currentColor"/>
                  <path d="M210.464 658.432a27.808 27.808 0 1 0 28.608 27.84 28.224 28.224 0 0 0-28.608-27.84M64 416h96v96H64z m128 0h96v96h-96z m0-128h96v96h-96z m128 0h96v96h-96z m0 128h96v96h-96z m128 0h96v96h-96zM448 288h96v96h-96z m0-128h96v96h-96z" fill="currentColor"/>
                </svg>
                {{ config.actions[0].text }}
              </a>
              <a class="action theme-alt" :href="config.actions[1].link">
                {{ config.actions[1].text }}
              </a>
            </div>
          </div>
          <div class="preview-container">
            <div class="preview-image">
              <img :src=config.image alt="VIPER Preview">
            </div>
          </div>
        </div>
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
.hero-container {
  padding: 2rem;
}

.hero-section {
  height: calc(100vh - var(--vp-nav-height) - 4rem);
  min-height: 800px; /* 添加最小高度 */
  display: flex;
  align-items: flex-start;
  justify-content: center;
  text-align: center;
  position: relative;
  overflow: hidden;
  background-size: 200% 200%;
  animation: gradientBg 30s ease infinite;
  backdrop-filter: blur(10px);
  border-radius: 24px;
  padding: 2rem;
}

.gradient-hero {
  background: 
    /* 左上角 */
    radial-gradient(circle at 0% 0%, rgba(255, 71, 71, 0.85) 0%, transparent 25%),
    /* 右上角 */
    radial-gradient(circle at 100% 0%, rgba(123, 97, 255, 0.85) 0%, transparent 25%),
    /* 上边中间 */
    radial-gradient(circle at 50% 0%, rgba(255, 105, 180, 0.7) 0%, transparent 25%),
    /* 左边中间 */
    radial-gradient(circle at 0% 50%, rgba(0, 255, 255, 0.7) 0%, transparent 25%),
    /* 右边中间 */
    radial-gradient(circle at 100% 50%, rgba(191, 64, 255, 0.7) 0%, transparent 25%),
    /* 中心 */
    radial-gradient(circle at 50% 50%, rgba(255, 64, 255, 0.6) 0%, transparent 35%),
    /* 左下角 - 增加亮绿色 */
    radial-gradient(circle at 0% 100%, rgba(72, 255, 0, 0.8) 0%, transparent 25%),
    /* 右下角 */
    radial-gradient(circle at 100% 100%, rgba(64, 166, 255, 0.85) 0%, transparent 25%),
    /* 下边中间 - 增加亮黄色 */
    radial-gradient(circle at 50% 100%, rgba(255, 251, 0, 0.75) 0%, transparent 25%),
    /* 整体底色 - 稍微调亮 */
    linear-gradient(45deg, rgba(0, 0, 0, 0.89), rgba(0, 0, 0, 0.87));
  background-size: 150% 150%;
  animation: gradientFlow 30s ease infinite;
  backdrop-filter: blur(100px);
}

@keyframes gradientFlow {
  0% {
    background-position: 
      0% 0%, 100% 0%, 50% 0%,
      0% 50%, 100% 50%, 50% 50%,
      0% 100%, 100% 100%, 50% 100%,
      0% 0%;
  }
  25% {
    background-position: 
      15% 15%, 85% 15%, 65% 15%,
      15% 50%, 85% 50%, 35% 65%,
      15% 85%, 85% 85%, 35% 85%,
      15% 15%;
  }
  50% {
    background-position: 
      25% 25%, 75% 25%, 75% 25%,
      25% 50%, 75% 50%, 50% 75%,
      25% 75%, 75% 75%, 50% 75%,
      25% 25%;
  }
  75% {
    background-position: 
      15% 85%, 85% 85%, 65% 85%,
      15% 50%, 85% 50%, 35% 35%,
      15% 15%, 85% 15%, 35% 15%,
      15% 85%;
  }
  100% {
    background-position: 
      0% 0%, 100% 0%, 50% 0%,
      0% 50%, 100% 50%, 50% 50%,
      0% 100%, 100% 100%, 50% 100%,
      0% 0%;
  }
}

.main {
  max-width: 1400px;
  width: 100%;
  height: 100%;
  margin: 0 auto;
  display: flex;
  align-items: flex-start;
  justify-content: center;
  padding: 0;
}

.content {
  display: flex;
  flex-direction: column;
  align-items: center;
  gap: 0;
  max-width: 1400px;
  width: 100%;
  height: 100%;
}

.text {
  width: 100%;
  padding: 0 24px;
  display: flex;
  flex-direction: column;
  align-items: center;
  justify-content: center;
  gap: 1.5rem;
  flex-shrink: 0;
  padding-top: 2rem;
  padding-bottom: 3rem;
  background: transparent;
}

.name {
  font-size: clamp(4.2rem, 8.5vw, 7.8rem);
  line-height: 1;
  font-weight: 800;
  color: rgba(255, 255, 255, 1);
  text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
  white-space: nowrap;
  margin: 0;
  padding: 0;
  letter-spacing: -0.02em;
}

.tagline {
  font-size: clamp(1rem, 1.6vw, 1.4rem);
  line-height: 1.4;
  color: rgba(255, 255, 255, 0.95);
  text-shadow: 0 2px 3px rgba(0, 0, 0, 0.2);
  margin: 0 auto;
  max-width: 1400px;
  font-weight: 500;
  white-space: nowrap;
  overflow: hidden;
  text-overflow: ellipsis;
}

.actions {
  display: flex;
  gap: 1.5rem;
  flex-wrap: wrap;
  justify-content: center;
  margin-top: 1rem;
}

.action {
  display: inline-flex;
  align-items: center;
  padding: 1rem 2rem;
  border-radius: 12px;
  font-size: 1.25rem;
  font-weight: 600;
  transition: all 0.3s ease;
  text-decoration: none;
  text-shadow: 0 1px 2px rgba(0, 0, 0, 0.1);
  position: relative; /* 添加相对定位 */
}

/* 添加外环基础样式 */
.action::before {
  content: '';
  position: absolute;
  inset: -4px; /* 减小外环距离 */
  border-radius: 13px; /* 相应调整圆角 */
  padding: 1px; /* 减小外环粗细 */
  background: linear-gradient(
    45deg,
    rgba(255, 255, 255, 0.1),
    rgba(255, 255, 255, 0.2),
    rgba(255, 255, 255, 0.3),
    rgba(255, 255, 255, 0.2),
    rgba(255, 255, 255, 0.1)
  );
  -webkit-mask: linear-gradient(#fff 0 0) content-box, linear-gradient(#fff 0 0);
  -webkit-mask-composite: xor;
  mask-composite: exclude;
  background-size: 200% 200%;
  animation: none;
  opacity: 0.4; /* 稍微降低默认透明度 */
  transition: opacity 0.3s ease;
}

/* 鼠标悬停时激活流光动画 */
.action:hover::before {
  animation: shine 2s linear infinite;
  opacity: 1;
}

/* 流光动画 */
@keyframes shine {
  0% {
    background-position: 200% 0;
  }
  100% {
    background-position: -200% 0;
  }
}

/* 修改现有的主题按钮样式 */
.theme-brand {
  background: var(--vp-c-white);
  color: var(--vp-c-black);
  border: none;
  box-shadow: 0 4px 15px rgba(255, 255, 255, 0.3);
}

.theme-brand:hover {
  background: rgba(255, 255, 255, 0.95);
  color: var(--vp-c-black);
  transform: translateY(-2px);
  box-shadow: 0 6px 20px rgba(255, 255, 255, 0.4);
}

.theme-alt {
  background: rgba(0, 0, 0, 0.8);
  color: var(--vp-c-white);
  border: 1px solid rgba(255, 255, 255, 0.2);
}

.theme-alt:hover {
  background: rgba(0, 0, 0, 0.9);
  border-color: rgba(255, 255, 255, 0.3);
  transform: translateY(-2px);
}

.preview-container {
  position: relative;
  width: 100%;
  flex: 1;
  min-height: 0;
  display: flex;
  flex-direction: column;
  margin-bottom: -2rem;
}

.preview-image {
  position: absolute;
  inset: 0;
  padding: 0 1rem;
  overflow: hidden;
}

.preview-image img {
  width: 100%;
  height: 100%;
  object-fit: cover;
  object-position: top;
  border-radius: 16px 16px 0 0;
  box-shadow: 0 8px 24px rgba(0, 0, 0, 0.2);
}

@media (max-width: 960px) {
  .hero-container {
    padding: 1rem;
  }

  .hero-section {
    min-height: 500px; /* 中等屏幕的最小高度 */
    padding: 2rem;
  }

  .name {
    font-size: clamp(3.5rem, 7vw, 5.6rem);
    white-space: normal;
    text-align: center;
  }

  .text {
    padding: 0;
    padding-bottom: 2rem;
    gap: 1.2rem;
  }

  .preview-container {
    margin-bottom: -2rem;
  }

  .preview-image img {
    border-radius: 16px 16px 0 0;
  }

  .tagline {
    font-size: clamp(0.9rem, 1.4vw, 1.2rem);
    white-space: normal;
    text-align: center;
  }
}

@media (max-width: 640px) {
  .hero-container {
    padding: 0.5rem 0.5rem 0 0.5rem;
  }

  .hero-section {
    min-height: 450px; /* 小屏幕的最小高度 */
    padding: 1.5rem 1.5rem 0 1.5rem;
    border-radius: 16px;
  }

  .content {
    gap: 1rem;
  }
}

:deep(.dark) .hero-section {
  background-blend-mode: overlay;
}

/* 添加光晕效果 */
.hero-section::before {
  content: '';
  position: absolute;
  top: 0;
  left: 0;
  right: 0;
  bottom: 0;
  background: inherit;
  filter: blur(20px);
  opacity: 0.7;
  z-index: -1;
}

/* 移除之前的暗色主题叠加层 */
:deep(.dark) .hero-section::after {
  display: none;
}

.docker-icon {
  width: 1.2em;
  height: 1.2em;
  margin-right: 0.5em;
  transition: transform 0.3s ease;
}

.action.theme-brand {
  display: inline-flex;
  align-items: center;
  gap: 0.25em;
}

.action.theme-brand:hover .docker-icon {
  transform: scale(1.1);
}
</style>
