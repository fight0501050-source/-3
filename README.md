<!DOCTYPE html>
<html lang="zh-TW">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>教師學科知能評量－社會科高頻考點衝刺測驗系統</title>
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  <!-- Phosphor Icons -->
  <script src="https://unpkg.com/@phosphor-icons/web"></script>
  <style>
    @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;500;700;900&display=swap');
    body {
      font-family: 'Noto Sans TC', sans-serif;
    }
    .custom-scrollbar::-webkit-scrollbar {
      width: 6px;
    }
    .custom-scrollbar::-webkit-scrollbar-track {
      background: #f1f5f9;
    }
    .custom-scrollbar::-webkit-scrollbar-thumb {
      background: #cbd5e1;
      border-radius: 4px;
    }
  </style>
</head>
<body class="bg-slate-100 text-slate-800 min-h-screen flex flex-col">

  <!-- Header -->
  <header class="bg-indigo-700 text-white shadow-md sticky top-0 z-50">
    <div class="max-w-5xl mx-auto px-4 py-3 flex items-center justify-between">
      <div class="flex items-center space-x-3">
        <i class="ph-bold ph-graduation-cap text-2xl text-amber-300"></i>
        <div>
          <h1 class="text-lg md:text-xl font-bold tracking-tight">社會科學科知能評量 互動題庫</h1>
          <p class="text-xs text-indigo-200">歷史・地理・公民 高頻真題考點速記</p>
        </div>
      </div>
      <div class="flex items-center space-x-2 text-xs md:text-sm">
        <button id="navCheatSheetBtn" class="px-3 py-1.5 rounded-lg bg-indigo-600 hover:bg-indigo-500 font-medium transition flex items-center gap-1">
          <i class="ph-bold ph-book-open"></i> 考點速記卡
        </button>
        <button id="navQuizBtn" class="px-3 py-1.5 rounded-lg bg-amber-500 hover:bg-amber-400 text-indigo-950 font-bold transition flex items-center gap-1">
          <i class="ph-bold ph-pencil-simple-line"></i> 測驗練習
        </button>
      </div>
    </div>
  </header>

  <!-- Main Container -->
  <main class="flex-1 max-w-5xl w-full mx-auto p-4 md:p-6">

    <!-- 視圖 1: 考點速記卡 (Cheat Sheet) -->
    <section id="viewCheatSheet" class="hidden space-y-6">
      <div class="bg-white p-6 rounded-2xl shadow-sm border border-slate-200">
        <h2 class="text-xl font-bold text-slate-800 flex items-center gap-2 mb-4">
          <i class="ph-fill ph-lightbulb text-amber-500"></i> 考前核心衝刺：核心觀念對照表
        </h2>
        
        <div class="grid grid-cols-1 md:grid-cols-3 gap-4">
          <!-- 公民 -->
          <div class="border border-indigo-100 rounded-xl p-4 bg-indigo-50/50">
            <h3 class="font-bold text-indigo-900 border-b border-indigo-200 pb-2 mb-3 flex items-center justify-between">
              <span>公民：經濟與社會</span>
              <span class="text-xs bg-indigo-200 text-indigo-800 px-2 py-0.5 rounded">常考必背</span>
            </h3>
            <ul class="text-xs space-y-2 text-slate-700 leading-relaxed">
              <li><strong>機會成本</strong>＝外顯成本（實付）＋隱含成本（放棄之最高收入）。</li>
              <li><strong>全球在地化 vs 在地全球化</strong>：外商品牌依在地調整（如素食麥當勞、星巴克媽祖杯）vs 在地優勢輸出國際（如珍奶標準化海外展店）。</li>
              <li><strong>失業型態</strong>：自然失業＝摩擦性（換工作/求職待業）＋結構性（技能不符/產業外移）。景氣蕭條＝循環性。</li>
              <li><strong>菲力普曲線</strong>：通膨率與失業率反向變動；高失業＋高通膨＝「停滯性通膨」。</li>
              <li><strong>痛苦指數</strong>＝失業率 ＋ 通貨膨脹率。</li>
              <li><strong>純公共財 vs 準公共財</strong>：純＝無排他、無敵對（國防、路燈）；準＝具排他、無敵對（收費影城、非壅塞高速公路）。</li>
            </ul>
          </div>

          <!-- 歷史 -->
          <div class="border border-emerald-100 rounded-xl p-4 bg-emerald-50/50">
            <h3 class="font-bold text-emerald-900 border-b border-emerald-200 pb-2 mb-3 flex items-center justify-between">
              <span>歷史：台灣史關鍵點</span>
              <span class="text-xs bg-emerald-200 text-emerald-800 px-2 py-0.5 rounded">年代脈絡</span>
            </h3>
            <ul class="text-xs space-y-2 text-slate-700 leading-relaxed">
              <li><strong>清領重心轉移</strong>：1860年開港通商後，茶葉與樟腦外銷，經濟重心由南轉北，淡水港（大稻埕）崛起。</li>
              <li><strong>牡丹社事件（1874）</strong>：日軍登陸琅嶠（恆春），沈葆楨來台督辦海防，促成恆春建城與開山撫番。</li>
              <li><strong>日治農民抗爭</strong>：1925二林事件（蔗農反抗製糖會社壓榨）；1930年代蓬萊米高利潤引發「米糖相剋」。</li>
              <li><strong>西來庵事件（1915）</strong>：余清芳領導，台灣最後一次大規模武裝抗日，後轉為政治社會運動。</li>
              <li><strong>重要水圳</strong>：彰化八堡圳（施世榜）、高雄曹公圳（曹謹）、台北瑠公圳（郭錫瑠）。</li>
            </ul>
          </div>

          <!-- 地理與法律 -->
          <div class="border border-sky-100 rounded-xl p-4 bg-sky-50/50">
            <h3 class="font-bold text-sky-900 border-b border-sky-200 pb-2 mb-3 flex items-center justify-between">
              <span>地理與法律體系</span>
              <span class="text-xs bg-sky-200 text-sky-800 px-2 py-0.5 rounded">觀念陷阱</span>
            </h3>
            <ul class="text-xs space-y-2 text-slate-700 leading-relaxed">
              <li><strong>地方特有風向</strong>：落山風（恆春10-4月東北季風過山下坡風）；九降風（新竹乾燥強風，造就米粉與柿餅）；焚風（中央山脈背風坡乾熱風）。</li>
              <li><strong>法律位階</strong>：憲法 ＞ 法律 ＞ 法規命令 ＞ 自治條例 ＞ 自治規則 ＞ 行政規則。</li>
              <li><strong>遺產法定繼承</strong>：配偶與第一順位直系血親卑親屬（子女）同為繼承人時，應繼分「平均分配」。</li>
              <li><strong>立法院席次</strong>：共113席（區域73席＋不分區政黨34席＋平地原住民3席＋山地原住民3席）。</li>
            </ul>
          </div>
        </div>
      </div>
    </section>

    <!-- 視圖 2: 測驗練習 (Quiz View) -->
    <section id="viewQuiz" class="space-y-6">

      <!-- 控制面板與篩選 -->
      <div class="bg-white p-4 rounded-xl shadow-sm border border-slate-200 flex flex-wrap items-center justify-between gap-4">
        <div class="flex flex-wrap items-center gap-2" id="filterTabs">
          <button data-cat="all" class="cat-btn active px-3.5 py-1.5 rounded-lg text-sm font-semibold bg-indigo-600 text-white shadow-sm transition">全部題庫 (<span id="countAll">0</span>)</button>
          <button data-cat="歷史" class="cat-btn px-3.5 py-1.5 rounded-lg text-sm font-semibold bg-slate-100 hover:bg-slate-200 text-slate-700 transition">歷史篇 (<span id="countHist">0</span>)</button>
          <button data-cat="地理" class="cat-btn px-3.5 py-1.5 rounded-lg text-sm font-semibold bg-slate-100 hover:bg-slate-200 text-slate-700 transition">地理篇 (<span id="countGeo">0</span>)</button>
          <button data-cat="公民" class="cat-btn px-3.5 py-1.5 rounded-lg text-sm font-semibold bg-slate-100 hover:bg-slate-200 text-slate-700 transition">公民與社會 (<span id="countCivic">0</span>)</button>
          <button id="wrongOnlyBtn" class="px-3.5 py-1.5 rounded-lg text-sm font-semibold bg-rose-50 hover:bg-rose-100 text-rose-700 border border-rose-200 transition flex items-center gap-1">
            <i class="ph-bold ph-warning-circle"></i> 只做錯題 (<span id="countWrong">0</span>)
          </button>
        </div>

        <div class="flex items-center gap-3 text-sm">
          <span class="text-slate-500 font-medium">答題進度: <span id="progressText" class="text-indigo-600 font-bold">0 / 0</span></span>
          <button id="resetAllBtn" class="text-xs text-slate-400 hover:text-slate-600 underline">重置所有答題紀錄</button>
        </div>
      </div>

      <!-- 測驗題卡主容器 -->
      <div id="quizContainer" class="bg-white p-6 md:p-8 rounded-2xl shadow-sm border border-slate-200 relative min-h-[420px] flex flex-col justify-between">
        
        <!-- 頂部題號與分類標籤 -->
        <div>
          <div class="flex items-center justify-between mb-4 pb-3 border-b border-slate-100">
            <div class="flex items-center gap-2">
              <span id="badgeCategory" class="px-2.5 py-1 rounded-md text-xs font-bold bg-indigo-100 text-indigo-700">公民科</span>
              <span id="badgeSubtopic" class="text-xs text-slate-400 font-medium">經濟學重點</span>
            </div>
            <div class="text-sm font-semibold text-slate-400">
              第 <span id="currentQIndex" class="text-slate-800 text-base">1</span> / <span id="totalQIndex">25</span> 題
            </div>
          </div>

          <!-- 題目文字 -->
          <h3 id="questionText" class="text-lg md:text-xl font-bold text-slate-800 leading-relaxed mb-6">
            題目載入中...
          </h3>

          <!-- 選項容器 -->
          <div id="optionsContainer" class="space-y-3 mb-6">
            <!-- 動態生成選項 -->
          </div>

          <!-- 解題精華與詳解卡 (答題後顯示) -->
          <div id="rationaleBox" class="hidden p-4 rounded-xl border bg-slate-50 transition-all duration-200">
            <div class="flex items-start gap-2">
              <i id="rationaleIcon" class="ph-fill ph-check-circle text-xl mt-0.5 text-emerald-600"></i>
              <div class="text-sm space-y-1">
                <div id="rationaleTitle" class="font-bold text-slate-800">答題正確！</div>
                <div id="rationaleContent" class="text-slate-600 leading-relaxed"></div>
              </div>
            </div>
          </div>
        </div>

        <!-- 底部切換列 -->
        <div class="flex items-center justify-between pt-6 border-t border-slate-100 mt-6">
          <button id="prevBtn" class="px-4 py-2 rounded-lg bg-slate-100 hover:bg-slate-200 text-slate-700 font-semibold text-sm transition flex items-center gap-1 disabled:opacity-40 disabled:cursor-not-allowed">
            <i class="ph-bold ph-caret-left"></i> 上一題
          </button>
          
          <div class="flex items-center gap-2">
            <button id="skipBtn" class="px-4 py-2 rounded-lg text-slate-500 hover:bg-slate-100 font-medium text-sm transition">
              跳過此題
            </button>
            <button id="nextBtn" class="px-5 py-2 rounded-lg bg-indigo-600 hover:bg-indigo-700 text-white font-bold text-sm transition flex items-center gap-1 shadow-sm">
              下一題 <i class="ph-bold ph-caret-right"></i>
            </button>
          </div>
        </div>

      </div>

      <!-- 快速跳題導航抽屜 -->
      <div class="bg-white p-4 rounded-xl shadow-sm border border-slate-200">
        <h4 class="text-xs font-bold text-slate-400 uppercase tracking-wider mb-3 flex items-center justify-between">
          <span>題目快速索引</span>
          <span class="text-[11px] text-slate-400 font-normal">綠色：正確 | 紅色：錯誤 | 灰色：未作答</span>
        </h4>
        <div id="questionGrid" class="flex flex-wrap gap-2 max-h-36 overflow-y-auto custom-scrollbar p-1">
          <!-- 動態生成題目按鈕 -->
        </div>
      </div>

    </section>

  </main>

  <!-- Footer -->
  <footer class="bg-white border-t border-slate-200 py-3 text-center text-xs text-slate-400 mt-auto">
    教師甄試 / 學科知能評量 (社會領域) 專用互動題庫系統
  </footer>

  <!-- 題庫與核心邏輯 JavaScript -->
  <script>
    // 嚴選題庫資料（緊扣所附學科知能評量重點筆記）
    const rawQuestions = [
      {
        id: 1,
        cat: "公民",
        topic: "經濟學／全球化",
        question: "跨國連鎖餐飲品牌進入印度市場時推出「素食漢堡」、在台灣推出「米漢堡」或星巴克馬克杯印上大甲媽祖圖樣，此種現象屬於下列何者？",
        options: [
          { text: "全球在地化 (Glocalization)", correct: true },
          { text: "在地全球化 (Localization-globalization)", correct: false },
          { text: "文化失調 (Cultural lag)", correct: false },
          { text: "跨國水平分工 (Horizontal division)", correct: false }
        ],
        explanation: "全球在地化：全球性品牌或理念進入特定地區時，為了適應在地宗教、文化或消費習慣量身打造調整。若是在地特色商品推廣至全球市場（如珍奶標準化海外展店），則為「在地全球化」。"
      },
      {
        id: 2,
        cat: "公民",
        topic: "經濟學／機會成本",
        question: "小明放棄原本每小時時薪 1,000 元的家教工作 2 小時，選擇去與朋友看電影花費 500 元、吃飯花費 800 元。請問小明此次約會的「機會成本」是多少元？",
        options: [
          { text: "1,300 元", correct: false },
          { text: "2,000 元", correct: false },
          { text: "3,300 元", correct: true },
          { text: "2,500 元", correct: false }
        ],
        explanation: "機會成本 ＝ 外顯成本（實際支付：電影 500 ＋ 餐費 800 ＝ 1,300）＋ 隱含成本（放棄的最高報酬收入：2小時 × 1000 ＝ 2,000），總計 3,300 元。"
      },
      {
        id: 3,
        cat: "地理",
        topic: "台灣氣候與風向",
        question: "每年農曆九月後，東北季風穿越管狀的台灣海峽，抵達新竹時風力強勁且異常乾燥，當地著名特產米粉與柿餅常藉此風吹乾。此風稱為？",
        options: [
          { text: "落山風", correct: false },
          { text: "九降風", correct: true },
          { text: "焚風", correct: false },
          { text: "西北雨", correct: false }
        ],
        explanation: "新竹九降風是東北季風受台灣海峽地形壓縮形成的強烈乾燥下沉風；落山風則特指恆春半島10月至翌年4月的下坡乾冷風；焚風則是越過山脈背風坡的乾熱風。"
      },
      {
        id: 4,
        cat: "歷史",
        topic: "清領時期經濟與港口",
        question: "清領時期（特別是 1860 年天津條約簽訂開港通商後），哪一項外銷作物的蓬勃發展促成了台灣經濟重心「由南向北轉移」？主要出口港與市街為何？",
        options: [
          { text: "甘蔗／打狗港（旗後）", correct: false },
          { text: "稻米／鹿港", correct: false },
          { text: "茶葉／淡水港（大稻埕）", correct: true },
          { text: "樟腦／安平港", correct: false }
        ],
        explanation: "1860年台灣開港通商後，北部丘陵大量種植茶葉，經由大稻埕加工並由淡水港外銷，產值超越南部糖米，台灣經濟重心由南向北移。"
      },
      {
        id: 5,
        cat: "歷史",
        topic: "清領外力衝擊",
        question: "西元 1874 年（同治 13 年），日軍藉琉球宮古島船難事件登陸瑯嶠（今恆春），排灣族於石門奮勇抗日。清廷派何人來台督辦海防並開始積極推動開山撫番？",
        options: [
          { text: "劉銘傳", correct: false },
          { text: "沈葆楨", correct: true },
          { text: "施琅", correct: false },
          { text: "陳永華", correct: false }
        ],
        explanation: "此為牡丹社事件。事件後清廷派福州船政大臣沈葆楨來台督辦海防，隨後奏請增設恆春縣、闢建八通關等古道（開山撫番），並廢除漢人渡台三禁。"
      },
      {
        id: 6,
        cat: "公民",
        topic: "總體經濟與就業",
        question: "大學畢業生剛離校正在尋找第一份合適的正職，或是上班族為了轉換跑道主動離職尋職期間所產生的暫時性未就業狀態，在經濟學上屬於哪種類型失業？",
        options: [
          { text: "摩擦性失業", correct: true },
          { text: "結構性失業", correct: false },
          { text: "循環性失業", correct: false },
          { text: "季節性失業", correct: false }
        ],
        explanation: "摩擦性失業屬於求職或換工作過程中，因尋職資訊不對稱與時間差產生的短暫自願性失業。若為技能與產業需求脫節（如AI取代技術）則為結構性失業；自然失業率即為兩者相加。"
      },
      {
        id: 7,
        cat: "公民",
        topic: "法律位階與規範",
        question: "依據我國中央法規標準法與地方制度法，關於各級法律規範的效力位階，由高到低的正確順序為何？",
        options: [
          { text: "憲法 ＞ 法律 ＞ 法規命令 ＞ 自治條例 ＞ 自治規則 ＞ 行政規則", correct: true },
          { text: "憲法 ＞ 法律 ＞ 自治條例 ＞ 法規命令 ＞ 行政規則 ＞ 自治規則", correct: false },
          { text: "法律 ＞ 憲法 ＞ 法規命令 ＞ 自治條例 ＞ 自治規則", correct: false },
          { text: "憲法 ＞ 法規命令 ＞ 法律 ＞ 自治條例 ＞ 行政規則", correct: false }
        ],
        explanation: "法規效力階層：憲法最高，其次為立法院制定的法律，接著為行政機關受法律授權之法規命令，其後依序為地方議會通過的自治條例、地方政府訂定的自治規則、內部業務指導之行政規則。"
      },
      {
        id: 8,
        cat: "公民",
        topic: "民法親屬與繼承",
        question: "依據我國民法規定，某甲死亡留有遺產 600 萬元，且未立遺囑。甲遺有配偶乙，以及兩名子女丙、丁。請問此筆 600 萬元遺產依法應如何分配？",
        options: [
          { text: "配偶乙獨得 300 萬，丙與丁各分得 150 萬元", correct: false },
          { text: "配偶乙、子女丙、子女丁各平均繼承 200 萬元", correct: true },
          { text: "配偶乙取得 600 萬全部，子女無繼承權", correct: false },
          { text: "子女各分得 300 萬元，配偶僅享有剩餘財產請求權", correct: false }
        ],
        explanation: "民法第 1144 條第 1 款規定：配偶與第一順位繼承人（直系血親卑親屬）同為繼承時，其應繼分與他繼承人平均。故配偶、長子、次子三人均分，每人各 200 萬元。"
      },
      {
        id: 9,
        cat: "地理",
        topic: "台灣地質與地形",
        question: "台灣離島中，小琉球與澎湖群島在地質地形的成因分類上，分別屬於下列何者？",
        options: [
          { text: "小琉球：珊瑚礁島；澎湖：火山島（柱狀玄武岩）", correct: true },
          { text: "小琉球：大陸島；澎湖：珊瑚礁島", correct: false },
          { text: "小琉球：火山島；澎湖：大陸島", correct: false },
          { text: "小琉球：沈積岩島；澎湖：沙洲島", correct: false }
        ],
        explanation: "澎湖群島、綠島、蘭嶼、龜山島為火山活動形成的火山島（澎湖以柱狀玄武岩聞名）；小琉球為珊瑚礁隆起形成之珊瑚礁島；金門與馬祖則屬於大陸島。"
      },
      {
        id: 10,
        cat: "歷史",
        topic: "日治時期社會抗爭與運動",
        question: "西元 1915 年余清芳等人利用台南西來庵為據點，發動抗日事件（噍吧哖事件）。此事件對後續台灣抗日運動型態帶來何種重大轉折？",
        options: [
          { text: "促成原住民發動霧社事件", correct: false },
          { text: "標誌大規模武裝抗日結束，知識分子轉向非武裝的政治與文化社會運動", correct: true },
          { text: "促使清廷出兵與日本簽署天津條約", correct: false },
          { text: "導致總督府立即廢除保甲制度與警察制度", correct: false }
        ],
        explanation: "西來庵事件（噍吧哖事件）是日治時期台灣漢人最後一次大規模武裝抗日事件。遭強烈血腥鎮壓後，台灣菁英（如林獻堂、蔣渭水）體認到武裝起事不可行，轉而採取創辦文協、請願運動等體制內抗爭。"
      },
      {
        id: 11,
        cat: "歷史",
        topic: "日治現代化建設與總督府",
        question: "日治時期民政長官後藤新平推行「三大調查」，奠定殖民統治基礎。下列何者不屬於這「三大調查」？",
        options: [
          { text: "土地調查（清理隱田、確立產權）", correct: false },
          { text: "臨時臺灣舊慣調查（律法與風俗）", correct: false },
          { text: "戶口普查（國勢調查）", correct: false },
          { text: "全島水利開發大普查", correct: true }
        ],
        explanation: "後藤新平的三大調查為：1. 土地調查（清理隱田確立地權）、2. 臨時臺灣舊慣調查（掌握風俗法俗）、3. 人口調查（1905年第一次戶口普查/國勢調查）。水利調查不屬其列。"
      },
      {
        id: 12,
        cat: "公民",
        topic: "憲法與政府組織職權",
        question: "在台灣現行五權分立制度下，若監察院彈劾違法失職之公務人員或政務官，應移送哪一個機關進行實質審理並裁定懲戒處分？",
        options: [
          { text: "司法院懲戒法院", correct: true },
          { text: "司法院憲法法庭", correct: false },
          { text: "行政院公務人員保障培訓委員會", correct: false },
          { text: "考試院考選部", correct: false }
        ],
        explanation: "公務人員彈劾案由監察院提出後，移送「司法院懲戒法院」審理判定；「憲法法庭」主要職權為解釋憲法法規、總統副總統彈劾案及政黨解散案。"
      },
      {
        id: 13,
        cat: "公民",
        topic: "財貨分類與公共財",
        question: "經濟學中將財貨分為純公共財、準公共財（俱樂部財）、共有資源等。下列哪一組項目皆屬於「無排他性、無敵對性」的「純公共財」？",
        options: [
          { text: "國防安全、港口燈塔、路燈照明", correct: true },
          { text: "有線電視、電影院、市立公園", correct: false },
          { text: "收費高速公路、高爾夫球場、自來水", correct: false },
          { text: "深海漁業資源、公有牧場、圖書館付費自習室", correct: false }
        ],
        explanation: "純公共財具備「非排他性」（無法阻擋未付費者使用）與「非敵對性」（一人享用不減少他人效益），典型範例為國防、燈塔、氣象廣播與路燈。有線電視與電影具排他性，屬於準公共財。"
      },
      {
        id: 14,
        cat: "歷史",
        topic: "明鄭與清領土地制度",
        question: "明鄭時期為解決軍隊糧餉不足的問題，在陳永華建議下推行了何種開墾土地政策，並在今日台南、高雄一帶留下了「左營」、「前鎮」、「林鳳營」等軍事地名？",
        options: [
          { text: "寓兵於農（軍屯制度）", correct: true },
          { text: "官給墾照招募佃農", correct: false },
          { text: "全面沒收荷蘭王田改為私田拍賣", correct: false },
          { text: "設立土牛溝隔離界線", correct: false }
        ],
        explanation: "鄭成功與陳永華推行「寓兵於農」政策，軍隊設鎮安營、平日農耕自給戰時出征，土地分為官田、私田與營盤田，為台灣西南部奠定廣大農業拓墾基礎。"
      },
      {
        id: 15,
        cat: "地理",
        topic: "台灣海岸與地形特色",
        question: "若沿台灣海岸線從台中港出發「往南進行環島旅行」，依序見到的海岸自然景觀形態為何？",
        options: [
          { text: "平直沙灘與潟湖（西部）→ 裙礁珊瑚礁海岸（南部）→ 斷崖峭壁岩岸（東部）", correct: true },
          { text: "岬角灣澳岩岸 → 珊瑚礁海岸 → 泥灘地沙岸", correct: false },
          { text: "斷崖峭壁 → 平直沙灘 → 沉降峽灣", correct: false },
          { text: "珊瑚礁海岸 → 潟湖沙灘 → 三角洲平原", correct: false }
        ],
        explanation: "台灣西部為平直淤積的泥沙質海岸（沙洲、潟湖）；恆春半島南部為隆起之裙礁珊瑚礁海岸；東部（花蓮清水斷崖）為板塊碰撞隆起的斷崖峭壁岩岸；北部則為多岬灣的沈降岬灣海岸。"
      },
      {
        id: 16,
        cat: "公民",
        topic: "中央銀行貨幣政策",
        question: "當國內景氣低迷、民間投資動能不足時，中央銀行採取「寬鬆貨幣政策」以刺激經濟，通常會使用下列哪一種手段？",
        options: [
          { text: "調降存款準備率與調降重貼現率", correct: true },
          { text: "提高重貼現率並在公開市場發行公債收回游資", correct: false },
          { text: "提高法定存款準備金比率", correct: false },
          { text: "縮減銀行放款額度並調高放款基準利率", correct: false }
        ],
        explanation: "央行寬鬆貨幣政策的措施包括：降低重貼現率（降低商銀借款成本）、調低存款準備率（釋放商銀借貸資金）、公開市場買入債券（注資市場），使市場資金充裕以提振投資。"
      },
      {
        id: 17,
        cat: "歷史",
        topic: "清領台灣建省與現代化",
        question: "清法戰爭（1884）後，清廷體認到台灣海防戰略地位重要，將台灣獨立設省並派任首任巡撫劉銘傳。劉銘傳在台推動的現代化建設中，不包含下列何者？",
        options: [
          { text: "在大稻埕創辦西學堂與電報學堂", correct: false },
          { text: "修築基隆至新竹段鐵路及大稻埕郵政總局", correct: false },
          { text: "創設台灣首座新式製糖會社（台灣製糖株式會社）", correct: true },
          { text: "鋪設打狗（高雄）至福州廈門之間的海底電報線", correct: false }
        ],
        explanation: "新式現代化製糖廠（如橋仔頭台灣製糖株式會社）是由日治初期總督府於1900年後主導建立，並非清領劉銘傳巡撫推動的政策。"
      },
      {
        id: 18,
        cat: "公民",
        topic: "總體經濟／通膨與痛苦指數",
        question: "經濟學中當一國同時面臨「高失業率」與「高通貨膨脹率（物價持續飛漲）」兩難困境，導致經濟停滯且民生痛苦指數破表，此種現象被稱為？",
        options: [
          { text: "停滯性通貨膨脹 (Stagflation)", correct: true },
          { text: "通貨緊縮 (Deflation)", correct: false },
          { text: "流動性陷阱 (Liquidity trap)", correct: false },
          { text: "完全充分就業 (Full employment)", correct: false }
        ],
        explanation: "停滯性通膨（Stagflation）指經濟增長停滯、失業率上升，同時伴隨高物價通膨，打破傳統菲力普曲線的互斥規律；此時「痛苦指數＝失業率＋通膨率」會急遽飆高。"
      },
      {
        id: 19,
        cat: "公民",
        topic: "刑法基本原理",
        question: "醫師為了挽救病患性命依醫學常規施行手術切除組織，或法警依法院確定判決合法執行死刑槍決，依法不構成刑法傷害或殺人罪。這是因為符合刑法上的何種概念？",
        options: [
          { text: "阻卻違法事由（業務正當行為、依法令行為）", correct: true },
          { text: "阻卻責任能力事由", correct: false },
          { text: "正當法律程序保障原則", correct: false },
          { text: "罪刑法定原則", correct: false }
        ],
        explanation: "構成要件該當之行為，若具備阻卻違法事由（如刑法第21條依法令行為、第22條業務上正當行為、第23條正當防衛、第24條緊急避難），即不具實質違法性，不成立犯罪。"
      },
      {
        id: 20,
        cat: "歷史",
        topic: "清領初期渡台禁令",
        question: "清廷平定台灣鄭氏政權後，康熙帝採納施琅《臺灣棄留疏》建言留台並頒布渡台禁令。下列關於「渡台三禁」的規範，何者敘述正確？",
        options: [
          { text: "渡台者必須申領官府許可執照，嚴格禁止攜帶家眷，且廣東潮惠人民禁止來台", correct: true },
          { text: "全面開放福建及廣東所有港口皆可自由直航安平港", correct: false },
          { text: "凡偷渡至台灣者，政府即配給開墾土地並豁免三年丁稅", correct: false },
          { text: "僅允許單身婦女來台與原住民通婚，男子嚴禁渡台", correct: false }
        ],
        explanation: "渡台三禁包括：1. 渡台需經官府核發照單；2. 渡台者不得攜眷，已在台者不得迎娶家眷；3. 粵地（廣東潮州、惠州）屢出海盜，嚴禁粵民來台。這也是造成早期台灣漢人社會男女比例失衡（有唐山公無唐山媽）的主因。"
      }
    ];

    // 狀態管理
    let activeCategory = 'all';
    let onlyWrong = false;
    let filteredQuestions = [];
    let currentIndex = 0;
    let userAnswers = {}; // { questionId: { selectedIndex, isCorrect } }

    // DOM 元素
    const filterTabs = document.getElementById('filterTabs');
    const wrongOnlyBtn = document.getElementById('wrongOnlyBtn');
    const questionText = document.getElementById('questionText');
    const optionsContainer = document.getElementById('optionsContainer');
    const rationaleBox = document.getElementById('rationaleBox');
    const rationaleTitle = document.getElementById('rationaleTitle');
    const rationaleContent = document.getElementById('rationaleContent');
    const rationaleIcon = document.getElementById('rationaleIcon');
    const badgeCategory = document.getElementById('badgeCategory');
    const badgeSubtopic = document.getElementById('badgeSubtopic');
    const currentQIndex = document.getElementById('currentQIndex');
    const totalQIndex = document.getElementById('totalQIndex');
    const prevBtn = document.getElementById('prevBtn');
    const nextBtn = document.getElementById('nextBtn');
    const skipBtn = document.getElementById('skipBtn');
    const questionGrid = document.getElementById('questionGrid');
    const progressText = document.getElementById('progressText');
    const resetAllBtn = document.getElementById('resetAllBtn');

    // 頁籤導覽
    const navCheatSheetBtn = document.getElementById('navCheatSheetBtn');
    const navQuizBtn = document.getElementById('navQuizBtn');
    const viewCheatSheet = document.getElementById('viewCheatSheet');
    const viewQuiz = document.getElementById('viewQuiz');

    // 初始化題數統計
    function updateCategoryCounts() {
      document.getElementById('countAll').textContent = rawQuestions.length;
      document.getElementById('countHist').textContent = rawQuestions.filter(q => q.cat === '歷史').length;
      document.getElementById('countGeo').textContent = rawQuestions.filter(q => q.cat === '地理').length;
      document.getElementById('countCivic').textContent = rawQuestions.filter(q => q.cat === '公民').length;
      
      const wrongCount = Object.values(userAnswers).filter(a => a.isCorrect === false).length;
      document.getElementById('countWrong').textContent = wrongCount;
    }

    // 篩選題目
    function applyFilter() {
      if (onlyWrong) {
        filteredQuestions = rawQuestions.filter(q => userAnswers[q.id] && userAnswers[q.id].isCorrect === false);
      } else if (activeCategory === 'all') {
        filteredQuestions = [...rawQuestions];
      } else {
        filteredQuestions = rawQuestions.filter(q => q.cat === activeCategory);
      }

      currentIndex = 0;
      renderQuestion();
      renderGrid();
      updateProgress();
    }

    // 渲染當前題目
    function renderQuestion() {
      if (filteredQuestions.length === 0) {
        questionText.textContent = "目前沒有符合條件的題目（若為錯題模式，表示尚無錯誤題目，表現優異！）。";
        optionsContainer.innerHTML = "";
        rationaleBox.classList.add('hidden');
        badgeCategory.textContent = "無題目";
        badgeSubtopic.textContent = "-";
        currentQIndex.textContent = "0";
        totalQIndex.textContent = "0";
        prevBtn.disabled = true;
        nextBtn.disabled = true;
        return;
      }

      const q = filteredQuestions[currentIndex];
      badgeCategory.textContent = q.cat + "學科";
      badgeSubtopic.textContent = q.topic;
      currentQIndex.textContent = currentIndex + 1;
      totalQIndex.textContent = filteredQuestions.length;
      questionText.textContent = q.question;

      prevBtn.disabled = currentIndex === 0;
      nextBtn.disabled = currentIndex === filteredQuestions.length - 1;

      // 檢查是否已作答
      const recorded = userAnswers[q.id];
      optionsContainer.innerHTML = "";

      q.options.forEach((opt, idx) => {
        const btn = document.createElement('button');
        btn.className = "w-full text-left p-4 rounded-xl border text-sm font-medium transition flex items-center justify-between ";
        
        if (!recorded) {
          btn.className += "border-slate-200 bg-white hover:bg-indigo-50/50 hover:border-indigo-300 text-slate-800";
          btn.innerHTML = `<span class="flex items-center gap-3"><span class="w-6 h-6 rounded-full bg-slate-100 text-slate-600 flex items-center justify-center font-bold text-xs">${String.fromCharCode(65 + idx)}</span>${opt.text}</span>`;
          btn.onclick = () => selectOption(idx);
        } else {
          // 已答過顯示狀態
          if (opt.correct) {
            btn.className += "border-emerald-500 bg-emerald-50 text-emerald-950 font-semibold";
            btn.innerHTML = `<span class="flex items-center gap-3"><span class="w-6 h-6 rounded-full bg-emerald-600 text-white flex items-center justify-center font-bold text-xs"><i class="ph-bold ph-check"></i></span>${opt.text}</span><span class="text-xs text-emerald-700 font-bold">正確解答</span>`;
          } else if (recorded.selectedIndex === idx && !opt.correct) {
            btn.className += "border-rose-400 bg-rose-50 text-rose-950 font-semibold";
            btn.innerHTML = `<span class="flex items-center gap-3"><span class="w-6 h-6 rounded-full bg-rose-500 text-white flex items-center justify-center font-bold text-xs"><i class="ph-bold ph-x"></i></span>${opt.text}</span><span class="text-xs text-rose-600 font-bold">您的選擇</span>`;
          } else {
            btn.className += "border-slate-200 bg-slate-50/60 text-slate-400 opacity-70";
            btn.innerHTML = `<span class="flex items-center gap-3"><span class="w-6 h-6 rounded-full bg-slate-200 text-slate-400 flex items-center justify-center font-bold text-xs">${String.fromCharCode(65 + idx)}</span>${opt.text}</span>`;
          }
          btn.disabled = true;
        }

        optionsContainer.appendChild(btn);
      });

      // 詳解卡狀態
      if (recorded) {
        rationaleBox.classList.remove('hidden');
        if (recorded.isCorrect) {
          rationaleBox.className = "p-4 rounded-xl border border-emerald-200 bg-emerald-50/80 transition-all";
          rationaleIcon.className = "ph-fill ph-check-circle text-xl text-emerald-600";
          rationaleTitle.textContent = "觀念答對！記住這道考點：";
          rationaleTitle.className = "font-bold text-emerald-900";
        } else {
          rationaleBox.className = "p-4 rounded-xl border border-rose-200 bg-rose-50/80 transition-all";
          rationaleIcon.className = "ph-fill ph-x-circle text-xl text-rose-600";
          rationaleTitle.textContent = "答案有誤，考點盲區提醒：";
          rationaleTitle.className = "font-bold text-rose-900";
        }
        rationaleContent.textContent = q.explanation;
      } else {
        rationaleBox.classList.add('hidden');
      }
    }

    // 選擇答案
    function selectOption(index) {
      const q = filteredQuestions[currentIndex];
      const isCorrect = q.options[index].correct;
      userAnswers[q.id] = { selectedIndex: index, isCorrect: isCorrect };

      updateCategoryCounts();
      renderQuestion();
      renderGrid();
      updateProgress();
    }

    // 更新索引格
    function renderGrid() {
      questionGrid.innerHTML = "";
      filteredQuestions.forEach((q, idx) => {
        const btn = document.createElement('button');
        btn.textContent = idx + 1;
        btn.className = "w-8 h-8 rounded-lg text-xs font-bold transition flex items-center justify-center ";
        
        const ans = userAnswers[q.id];
        if (idx === currentIndex) {
          btn.className += "ring-2 ring-indigo-600 ring-offset-1 ";
        }

        if (!ans) {
          btn.className += "bg-slate-100 text-slate-600 hover:bg-slate-200";
        } else if (ans.isCorrect) {
          btn.className += "bg-emerald-500 text-white";
        } else {
          btn.className += "bg-rose-500 text-white";
        }

        btn.onclick = () => {
          currentIndex = idx;
          renderQuestion();
          renderGrid();
        };

        questionGrid.appendChild(btn);
      });
    }

    // 更新作答進度
    function updateProgress() {
      const answeredTotal = Object.keys(userAnswers).length;
      progressText.textContent = `${answeredTotal} / ${rawQuestions.length}`;
    }

    // 事件監聽綁定
    prevBtn.onclick = () => {
      if (currentIndex > 0) {
        currentIndex--;
        renderQuestion();
        renderGrid();
      }
    };

    nextBtn.onclick = () => {
      if (currentIndex < filteredQuestions.length - 1) {
        currentIndex++;
        renderQuestion();
        renderGrid();
      }
    };

    skipBtn.onclick = () => {
      if (currentIndex < filteredQuestions.length - 1) {
        currentIndex++;
        renderQuestion();
        renderGrid();
      }
    };

    // 類別標籤切換
    filterTabs.addEventListener('click', (e) => {
      const btn = e.target.closest('.cat-btn');
      if (!btn) return;
      document.querySelectorAll('.cat-btn').forEach(b => {
        b.className = "cat-btn px-3.5 py-1.5 rounded-lg text-sm font-semibold bg-slate-100 hover:bg-slate-200 text-slate-700 transition";
      });
      btn.className = "cat-btn active px-3.5 py-1.5 rounded-lg text-sm font-semibold bg-indigo-600 text-white shadow-sm transition";
      
      onlyWrong = false;
      wrongOnlyBtn.className = "px-3.5 py-1.5 rounded-lg text-sm font-semibold bg-rose-50 hover:bg-rose-100 text-rose-700 border border-rose-200 transition flex items-center gap-1";
      activeCategory = btn.getAttribute('data-cat');
      applyFilter();
    });

    // 錯題模式切換
    wrongOnlyBtn.onclick = () => {
      onlyWrong = !onlyWrong;
      if (onlyWrong) {
        wrongOnlyBtn.className = "px-3.5 py-1.5 rounded-lg text-sm font-semibold bg-rose-600 text-white shadow-sm transition flex items-center gap-1";
        document.querySelectorAll('.cat-btn').forEach(b => {
          b.className = "cat-btn px-3.5 py-1.5 rounded-lg text-sm font-semibold bg-slate-100 hover:bg-slate-200 text-slate-700 transition";
        });
      } else {
        wrongOnlyBtn.className = "px-3.5 py-1.5 rounded-lg text-sm font-semibold bg-rose-50 hover:bg-rose-100 text-rose-700 border border-rose-200 transition flex items-center gap-1";
        document.querySelector(`.cat-btn[data-cat="${activeCategory}"]`).className = "cat-btn active px-3.5 py-1.5 rounded-lg text-sm font-semibold bg-indigo-600 text-white shadow-sm transition";
      }
      applyFilter();
    };

    // 重置所有紀錄
    resetAllBtn.onclick = () => {
      if (confirm("確定要清除所有練習紀錄與作答標記嗎？")) {
        userAnswers = {};
        updateCategoryCounts();
        applyFilter();
      }
    };

    // 切換考點卡與測驗模式
    navCheatSheetBtn.onclick = () => {
      viewCheatSheet.classList.remove('hidden');
      viewQuiz.classList.add('hidden');
      navCheatSheetBtn.className = "px-3 py-1.5 rounded-lg bg-amber-400 text-indigo-950 font-bold transition flex items-center gap-1";
      navQuizBtn.className = "px-3 py-1.5 rounded-lg bg-indigo-600 hover:bg-indigo-500 font-medium transition flex items-center gap-1";
    };

    navQuizBtn.onclick = () => {
      viewQuiz.classList.remove('hidden');
      viewCheatSheet.classList.add('hidden');
      navQuizBtn.className = "px-3 py-1.5 rounded-lg bg-amber-500 text-indigo-950 font-bold transition flex items-center gap-1";
      navCheatSheetBtn.className = "px-3 py-1.5 rounded-lg bg-indigo-600 hover:bg-indigo-500 font-medium transition flex items-center gap-1";
    };

    // 鍵盤快速鍵 (A, B, C, D 選擇，左右箭頭切換)
    window.addEventListener('keydown', (e) => {
      if (viewQuiz.classList.contains('hidden')) return;
      const key = e.key.toUpperCase();
      if (['A', 'B', 'C', 'D'].includes(key)) {
        const index = key.charCodeAt(0) - 65;
        const q = filteredQuestions[currentIndex];
        if (q && !userAnswers[q.id] && q.options[index]) {
          selectOption(index);
        }
      } else if (e.key === 'ArrowRight') {
        if (currentIndex < filteredQuestions.length - 1) {
          currentIndex++;
          renderQuestion();
          renderGrid();
        }
      } else if (e.key === 'ArrowLeft') {
        if (currentIndex > 0) {
          currentIndex--;
          renderQuestion();
          renderGrid();
        }
      }
    });

    // 初始載入
    updateCategoryCounts();
    applyFilter();
  </script>
</body>
</html>
```eof

### 系統特色與使用建議
1. **考點覆蓋完整**：
   - **歷史**：開港通商茶葉與重心北移、牡丹社事件、余清芳西來庵事件、後藤新平三大調查、明鄭寓兵於農軍屯地名、渡台三禁。
   - **地理**：新竹九降風、恆春落山風與焚風、火山島與珊瑚礁島地質辨析、環島海岸地形（沙岸→珊瑚礁→斷崖岩岸）。
   - **公民與社會**：機會成本精算（外顯＋隱含）、全球在地化與在地全球化案例、摩擦性/結構性失業、菲力普曲線與停滯性通膨、法規命令位階、遺產應繼分平均計算、阻卻違法事由。
2. **操作便捷**：
   - 支援滑鼠點擊或鍵盤快捷鍵（`A`、`B`、`C`、`D` 選擇，方向鍵 `←` / `→` 切換題目）。
   - 具備「考點速記卡」與「錯題過濾」功能，利於考前高效率刷題記憶。
