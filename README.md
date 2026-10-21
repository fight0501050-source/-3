<!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>學科知能評量－社會科完全題庫刷題系統 (72題完整版)</title>
  <!-- Tailwind CSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Phosphor Icons -->
  <script src="https://unpkg.com/@phosphor-icons/web"></script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;500;700;900&display=swap');
    body { font-family: 'Noto Sans TC', sans-serif; }
    .custom-scrollbar::-webkit-scrollbar { width: 6px; }
    .custom-scrollbar::-webkit-scrollbar-track { background: #f1f5f9; }
    .custom-scrollbar::-webkit-scrollbar-thumb { background: #cbd5e1; border-radius: 4px; }
  </style>
</head>
<body class="bg-slate-100 text-slate-800 min-h-screen flex flex-col">

  <!-- 頂部導航 -->
  <header class="bg-indigo-800 text-white shadow-md sticky top-0 z-50">
    <div class="max-w-5xl mx-auto px-4 py-3 flex items-center justify-between">
      <div class="flex items-center space-x-3">
        <i class="ph-bold ph-book-open-text text-2xl text-amber-300"></i>
        <div>
          <h1 class="text-lg md:text-xl font-bold tracking-tight">社會科學科知能評量・完整題庫刷題系統</h1>
          <p class="text-xs text-indigo-200">收錄文件內所有考點共 72 題精選題目</p>
        </div>
      </div>
      <div class="flex items-center space-x-2 text-xs md:text-sm">
        <button id="navQuizBtn" class="px-3 py-1.5 rounded-lg bg-amber-500 hover:bg-amber-400 text-indigo-950 font-bold transition flex items-center gap-1">
          <i class="ph-bold ph-pencil-simple"></i> 互動練習
        </button>
        <button id="navSummaryBtn" class="px-3 py-1.5 rounded-lg bg-indigo-700 hover:bg-indigo-600 font-medium transition flex items-center gap-1">
          <i class="ph-bold ph-cards"></i> 核心速記清單
        </button>
      </div>
    </div>
  </header>

  <!-- 主要內容區 -->
  <main class="flex-1 max-w-5xl w-full mx-auto p-4 md:p-6">

    <!-- 視圖 1: 測驗練習 (Quiz View) -->
    <section id="viewQuiz" class="space-y-6">

      <!-- 篩選列 -->
      <div class="bg-white p-4 rounded-xl shadow-sm border border-slate-200 flex flex-wrap items-center justify-between gap-4">
        <div class="flex flex-wrap items-center gap-2" id="filterTabs">
          <button data-cat="all" class="cat-btn active px-3 py-1.5 rounded-lg text-sm font-semibold bg-indigo-600 text-white shadow-sm transition">全部題庫 (<span id="countAll">0</span>)</button>
          <button data-cat="歷史" class="cat-btn px-3 py-1.5 rounded-lg text-sm font-semibold bg-slate-100 hover:bg-slate-200 text-slate-700 transition">歷史篇 (<span id="countHist">0</span>)</button>
          <button data-cat="地理" class="cat-btn px-3 py-1.5 rounded-lg text-sm font-semibold bg-slate-100 hover:bg-slate-200 text-slate-700 transition">地理篇 (<span id="countGeo">0</span>)</button>
          <button data-cat="公民" class="cat-btn px-3 py-1.5 rounded-lg text-sm font-semibold bg-slate-100 hover:bg-slate-200 text-slate-700 transition">公民篇 (<span id="countCivic">0</span>)</button>
          <button id="wrongOnlyBtn" class="px-3 py-1.5 rounded-lg text-sm font-semibold bg-rose-50 hover:bg-rose-100 text-rose-700 border border-rose-200 transition flex items-center gap-1">
            <i class="ph-bold ph-warning-circle"></i> 錯題複習 (<span id="countWrong">0</span>)
          </button>
        </div>

        <div class="flex items-center gap-3 text-sm">
          <span class="text-slate-500 font-medium">進度: <span id="progressText" class="text-indigo-600 font-bold">0 / 0</span></span>
          <button id="resetAllBtn" class="text-xs text-slate-400 hover:text-slate-600 underline">清空紀錄</button>
        </div>
      </div>

      <!-- 題目卡片 -->
      <div id="quizContainer" class="bg-white p-6 md:p-8 rounded-2xl shadow-sm border border-slate-200 relative min-h-[460px] flex flex-col justify-between">
        <div>
          <!-- 題目分類與序號 -->
          <div class="flex items-center justify-between mb-4 pb-3 border-b border-slate-100">
            <div class="flex items-center gap-2">
              <span id="badgeCategory" class="px-2.5 py-1 rounded-md text-xs font-bold bg-indigo-100 text-indigo-700">分類</span>
              <span id="badgeSubtopic" class="text-xs text-slate-400 font-medium">主題</span>
            </div>
            <div class="text-sm font-semibold text-slate-400">
              第 <span id="currentQIndex" class="text-slate-800 text-base">1</span> / <span id="totalQIndex">72</span> 題
            </div>
          </div>

          <!-- 題目內文 -->
          <h3 id="questionText" class="text-lg md:text-xl font-bold text-slate-800 leading-relaxed mb-6">題目載入中...</h3>

          <!-- 選項清單 -->
          <div id="optionsContainer" class="space-y-3 mb-6"></div>

          <!-- 解析提示區 -->
          <div id="rationaleBox" class="hidden p-4 rounded-xl border bg-slate-50 transition-all duration-200">
            <div class="flex items-start gap-2">
              <i id="rationaleIcon" class="ph-fill ph-check-circle text-xl mt-0.5 text-emerald-600"></i>
              <div class="text-sm space-y-1">
                <div id="rationaleTitle" class="font-bold text-slate-800">解析</div>
                <div id="rationaleContent" class="text-slate-600 leading-relaxed"></div>
              </div>
            </div>
          </div>
        </div>

        <!-- 下方換題控制 -->
        <div class="flex items-center justify-between pt-6 border-t border-slate-100 mt-6">
          <button id="prevBtn" class="px-4 py-2 rounded-lg bg-slate-100 hover:bg-slate-200 text-slate-700 font-semibold text-sm transition flex items-center gap-1 disabled:opacity-40 disabled:cursor-not-allowed">
            <i class="ph-bold ph-caret-left"></i> 上一題
          </button>
          
          <div class="flex items-center gap-2">
            <button id="skipBtn" class="px-4 py-2 rounded-lg text-slate-500 hover:bg-slate-100 font-medium text-sm transition">跳過</button>
            <button id="nextBtn" class="px-5 py-2 rounded-lg bg-indigo-600 hover:bg-indigo-700 text-white font-bold text-sm transition flex items-center gap-1 shadow-sm">
              下一題 <i class="ph-bold ph-caret-right"></i>
            </button>
          </div>
        </div>
      </div>

      <!-- 快速跳題矩陣 -->
      <div class="bg-white p-4 rounded-xl shadow-sm border border-slate-200">
        <h4 class="text-xs font-bold text-slate-400 uppercase tracking-wider mb-3 flex items-center justify-between">
          <span>快速索引導覽（點擊跳題）</span>
          <span class="text-[11px] text-slate-400 font-normal">綠：正確 ｜ 紅：錯誤 ｜ 灰：未作答</span>
        </h4>
        <div id="question
