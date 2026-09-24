<template>
  <div class="bg-white/10 backdrop-blur-lg rounded-2xl overflow-hidden border border-white/20 hover:border-cyan-400/50 transition-all hover:-translate-y-2 shadow-xl hover:shadow-cyan-500/20 group">
    <!-- 截图区域 -->
    <div class="aspect-video bg-slate-800 relative overflow-hidden">
      <img 
        :src="imageUrl" 
        :alt="title" 
        class="w-full h-full object-cover group-hover:scale-105 transition duration-500"
        @error="handleImageError"
      />
      <div class="absolute inset-0 bg-gradient-to-t from-slate-900/60 to-transparent"></div>
    </div>

    <!-- 文字信息区域 -->
    <div class="p-6 space-y-4">
      <h3 class="text-xl font-bold text-white">{{ title }}</h3>
      <p class="text-gray-300 text-sm leading-relaxed">{{ description }}</p>
      
      <!-- 技术标签 -->
      <div class="flex flex-wrap gap-2">
        <span 
          v-for="tag in tech.split(' + ')" 
          :key="tag" 
          class="px-3 py-1 bg-cyan-400/10 border border-cyan-400/30 rounded-full text-xs text-cyan-300"
        >
          {{ tag }}
        </span>
      </div>

      <!-- 操作按钮 -->
      <div class="flex gap-4 pt-2">
        <a 
          :href="demoUrl" 
          target="_blank" 
          class="flex-1 text-center px-4 py-2 bg-cyan-500 hover:bg-cyan-600 rounded-lg text-sm font-medium transition"
        >
          🔗 在线演示
        </a>
        <a 
          :href="codeUrl" 
          target="_blank" 
          class="flex-1 text-center px-4 py-2 bg-white/10 hover:bg-white/20 rounded-lg text-sm font-medium transition"
        >
          📂 查看代码
        </a>
      </div>
    </div>
  </div>
</template>

<script setup>
// 定义组件接收的属性（props）
defineProps({
  title: String,
  description: String,
  tech: String,
  demoUrl: String,
  codeUrl: String,
  imageUrl: String
})

// 如果图片加载失败，显示占位符
const handleImageError = (e) => {
  e.target.src = 'data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" width="400" height="225" viewBox="0 0 400 225"%3E%3Crect width="400" height="225" fill="%23334155"/%3E%3Ctext x="50%25" y="50%25" dominant-baseline="middle" text-anchor="middle" fill="%2394a3b8" font-size="16" font-family="sans-serif"%3E截图待更新%3C/text%3E%3C/svg%3E'
}
</script>