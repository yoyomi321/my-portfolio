<template>
  <div class="min-h-screen bg-gradient-to-br from-slate-900 via-purple-900 to-slate-900 text-white p-8">
    <!-- 顶部标题区 -->
    <header class="text-center py-12">
      <h1 class="text-5xl font-bold bg-gradient-to-r from-cyan-400 to-purple-400 bg-clip-text text-transparent">
                        我的数据可视化作品集
      </h1>
      <p class="text-gray-400 mt-4 text-lg">数字媒体技术 · 27届应届生 · 数据可视化前端开发</p>
      <div class="flex justify-center gap-6 mt-6 text-sm">
        <a href="#" class="text-cyan-400 hover:text-cyan-300 transition">GitHub</a>
        <a href="#" class="text-cyan-400 hover:text-cyan-300 transition">关于我</a>
      </div>
    </header>

    <!-- 作品卡片网格 -->
    <main class="max-w-6xl mx-auto grid md:grid-cols-2 lg:grid-cols-3 gap-8 py-12">
      <!-- 卡片 1：数据可视化大屏 -->
      <ProjectCard
        title="智慧校园数据大屏"
        description="多图表联动 · 实时数据 · 响应式适配"
        tech="Vue3 + ECharts + WebSocket"
        demoUrl="https://你的第一个项目链接.netlify.app"
        codeUrl="https://github.com/yoyomi321/dashboard-demo"
        imageUrl="/screenshots/dashboard.png"
      />

      <!-- 卡片 2：后台数据看板 -->
      <ProjectCard
        title="企业运营后台看板"
        description="表格筛选 · 图表联动 · 状态管理"
        tech="Vue3 + Element Plus + ECharts"
        demoUrl="https://你的第二个项目链接.netlify.app"
        codeUrl="https://github.com/yoyomi321/dataviz-dashboard"
        imageUrl="/screenshots/dataviz.png"
      />

      <!-- 卡片 3：3D 可视化项目 -->
      <ProjectCard
        title="3D 交互式数据看板"
        description="3D柱状图 · 旋转交互 · 悬停高亮"
        tech="Three.js + Vite + CanvasTexture"
        demoUrl="https://你的第三个项目链接.netlify.app"
        codeUrl="https://github.com/yoyomi321/my-3d-project"
        imageUrl="/screenshots/3d.png"
      />
    </main>

    <!-- 底部 -->
    <footer class="text-center text-gray-500 text-sm py-8 border-t border-gray-800">
      © 2026 你的名字 · 用 Vue3 + Vite + Tailwind CSS 构建
    </footer>
  </div>
</template>

<script setup>
import ProjectCard from './components/ProjectCard.vue'
</script>