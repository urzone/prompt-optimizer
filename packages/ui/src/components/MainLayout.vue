<template>
  <div class="min-h-screen bg-gradient-to-br from-indigo-900 via-purple-900 to-fuchsia-800 flex flex-col relative overflow-hidden">
    <!-- 背景装饰元素 -->
    <div class="absolute inset-0 overflow-hidden pointer-events-none">
      <div class="absolute -top-24 -right-24 w-96 h-96 bg-blue-500 opacity-20 rounded-full blur-3xl"></div>
      <div class="absolute top-1/3 -left-24 w-80 h-80 bg-purple-500 opacity-20 rounded-full blur-3xl"></div>
      <div class="absolute -bottom-24 right-1/3 w-72 h-72 bg-pink-500 opacity-20 rounded-full blur-3xl"></div>
    </div>
    
    <!-- 顶部导航栏 -->
    <header class="flex-none sticky top-0 z-40 bg-gradient-to-r from-indigo-800/80 to-purple-800/80 backdrop-blur-md border-b border-indigo-700/30 shadow-lg">
      <div class="container mx-auto px-3 sm:px-6 py-3 sm:py-4 flex justify-between items-center">
        <h1 class="text-lg sm:text-xl font-bold text-transparent bg-clip-text bg-gradient-to-r from-blue-300 to-purple-300 flex items-center gap-3">
          <img src="../assets/logo.jpg" alt="Logo" class="h-9 w-9 rounded-lg shadow-md transform hover:scale-105 transition-transform duration-300" />
          <slot name="title">Prompt Optimizer</slot>
        </h1>
        <div class="flex items-center gap-2 sm:gap-4">
          <slot name="actions"></slot>
        </div>
      </div>
    </header>

    <!-- 主要内容区域 -->
    <main class="flex-1 container mx-auto p-3 sm:p-5 overflow-hidden relative z-10">
      <div class="grid grid-cols-1 lg:grid-cols-2 gap-3 sm:gap-5 h-[calc(100vh-4rem)] sm:h-[calc(100vh-4.5rem)]">
        <slot></slot>
      </div>
    </main>

    <!-- 弹窗插槽 -->
    <slot name="modals"></slot>

    <!-- 全局提示 -->
    <ToastUI />
  </div>
</template>

<script setup>
import { ToastUI } from '../index'
</script>

<style>
.custom-select {
  -webkit-appearance: none !important;
  -moz-appearance: none !important;
  appearance: none !important;
  background-image: none !important;
}

.custom-select::-ms-expand {
  display: none;
}

/* 优化滚动条样式 */
::-webkit-scrollbar {
  width: 4px;
}

::-webkit-scrollbar-track {
  background: transparent;
}

::-webkit-scrollbar-thumb {
  background: rgba(255, 255, 255, 0.2);
  border-radius: 2px;
}

::-webkit-scrollbar-thumb:hover {
  background: rgba(255, 255, 255, 0.3);
}

/* 隐藏水平滚动条 */
::-webkit-scrollbar-horizontal {
  display: none;
}
</style>