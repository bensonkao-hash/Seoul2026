<!DOCTYPE html>
<html lang="zh-TW">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no, viewport-fit=cover">
    <title>SEOUL 2026 - 雲端版</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <script src="https://unpkg.com/lucide@latest"></script>
    <script src="https://cdnjs.cloudflare.com/ajax/libs/Sortable/1.15.0/Sortable.min.js"></script>
    <!-- 字體設定 -->
    <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@400;500;600;700;900&family=Cinzel:wght@400;500;600;700;800;900&family=Noto+Sans+KR:wght@500;700;900&display=swap" rel="stylesheet">
    
    <style>
        :root {
            --bg-deep: #050505;
            --glass-panel: rgba(30, 30, 30, 0.85);
            --glass-border: rgba(255, 255, 255, 0.15);
            --gold-primary: #D4AF37;
        }

        body {
            /* 全站統一字體設定 */
            font-family: 'Cinzel', 'Noto Serif TC', serif;
            font-weight: 600; 
            background-color: var(--bg-deep);
            color: #f2f2f2;
            -webkit-font-smoothing: antialiased;
            background-image: radial-gradient(circle at 50% -20%, #2a2415 0%, #000000 70%);
            height: 100dvh;
            overflow: hidden;
            overscroll-behavior: none;
            position: fixed;
            width: 100%;
        }

        .font-kr { font-family: 'Noto Sans KR', sans-serif; }
        .font-num { font-family: 'Cinzel', serif; }
        
        .no-scrollbar::-webkit-scrollbar { display: none; }
        .no-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }

        .glass {
            background: var(--glass-panel);
            backdrop-filter: blur(30px);
            -webkit-backdrop-filter: blur(30px);
            border: 1px solid var(--glass-border);
            box-shadow: 0 8px 32px 0 rgba(0, 0, 0, 0.5);
        }

        .glass-dock {
            background: rgba(15, 15, 15, 0.95);
            backdrop-filter: blur(40px);
            -webkit-backdrop-filter: blur(40px);
            border-top: 1px solid var(--glass-border);
            box-shadow: 0 -10px 50px rgba(0,0,0,0.8);
        }

        .text-gold-gradient {
            background: linear-gradient(135deg, #F9F1D0 0%, #D4AF37 40%, #C59D24 60%, #F9F1D0 100%);
            background-size: 200% auto;
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
            animation: shine 5s linear infinite;
        }
        @keyframes shine { to { background-position: 200% center; } }

        .fade-in { animation: fadeIn 0.4s ease-out forwards; opacity: 0; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(10px); } to { opacity: 1; transform: translateY(0); } }

        .slide-up { animation: slideUp 0.4s cubic-bezier(0.19, 1, 0.22, 1) forwards; transform: translateY(100%); }
        @keyframes slideUp { from { transform: translateY(100%); } to { transform: translateY(0); } }

        .btn-press:active { transform: scale(0.94); transition: transform 0.1s; }
        
        .pb-safe { padding-bottom: env(safe-area-inset-bottom, 20px); }
        .pt-safe { 
            padding-top: calc(env(safe-area-inset-top) + 24px);
        }

        .tab-content { display: none; opacity: 0; transition: opacity 0.3s ease; }
        .tab-content.active { display: block; opacity: 1; }

        input, select, textarea { font-family: 'Noto Serif TC', serif; font-weight: 600; }
        ::placeholder { color: #666; opacity: 1; font-weight: 500; }
        
        /* --- 核心修正：時間與日期輸入框 --- */
        input[type="date"], input[type="time"] {
            -webkit-appearance: none;
            appearance: none;
            background-color: #18181b;
            min-width: 0;
            width: 100%;
            box-sizing: border-box;
            display: block;
            text-align: left;
            padding-left: 1rem;
            padding-right: 1rem;
            
            font-family: 'Noto Serif TC', serif !important;
            font-weight: 500 !important;
            font-size: 1rem;
            color: white;
            
            height: 100%; 
            min-height: 56px; 
            
            /* 防止斷行 */
            white-space: nowrap;
            overflow: hidden;
        }

        input[type="date"]::-webkit-date-and-time-value,
        input[type="time"]::-webkit-date-and-time-value { 
            display: flex;
            align-items: center; 
            height: 100%;
            text-align: left;
        }

        #loading-screen {
            position: fixed; inset: 0; background: #000; z-index: 999;
            display: flex; justify-content: center; align-items: center;
            transition: opacity 0.5s;
        }
    </style>
</head>
<body class="flex flex-col text-sm tracking-wide selection:bg-yellow-900 selection:text-white">

    <!-- Loading Screen -->
    <div id="loading-screen">
        <div class="text-gold-gradient text-xl font-bold animate-pulse tracking-widest">CONNECTING...</div>
    </div>

    <!-- Header -->
    <header class="pt-safe px-6 pb-4 flex justify-between items-center z-20 flex-shrink-0 bg-gradient-to-b from-black/90 to-transparent">
        <h1 class="text-3xl font-extrabold text-white tracking-widest text-gold-gradient">SEOUL</h1>
        <!-- 右上角人員管理按鈕 -->
        <button onclick="openSubModal('modal-members')" class="w-10 h-10 rounded-full overflow-hidden border border-zinc-700 glass flex items-center justify-center shadow-[0_0_15px_rgba(212,175,55,0.2)] active:scale-90 transition group relative">
            <i data-lucide="users" size="18" class="text-yellow-600 group-hover:text-white transition"></i>
            <!-- 當前使用者指示點 -->
            <div id="user-indicator" class="hidden absolute bottom-1 right-1 w-1.5 h-1.5 bg-green-500 rounded-full"></div>
        </button>
    </header>

    <!-- Main Container -->
    <main class="flex-1 overflow-y-auto no-scrollbar relative pb-32 px-6" id="main-container">
        
        <!-- 0. Dashboard -->
        <div id="view-dashboard" class="tab-content active space-y-5 fade-in">
            <div class="mt-2 mb-6">
                <!-- 單行顯示 -->
                <h2 class="text-xl font-bold text-white tracking-wide whitespace-nowrap overflow-hidden text-ellipsis cursor-pointer" onclick="openSubModal('modal-members')">
                    早安，<span id="greeting-name" class="text-gold-gradient font-black">旅人</span>
                    <span id="greeting-hint" class="text-[10px] text-zinc-500 ml-1 font-normal hidden">(點此設定)</span>
                </h2>
                <p class="text-zinc-500 text-xs mt-1 tracking-widest font-bold">雲端同步中，隨時準備出發。</p>
            </div>

            <div class="grid grid-cols-2 gap-4">
                <!-- Weather -->
                <div class="glass rounded-[2rem] p-5 col-span-2 relative overflow-hidden flex items-center justify-between">
                    <div class="absolute -right-6 -top-6 w-32 h-32 bg-yellow-600/20 rounded-full blur-3xl"></div>
                    <div class="relative z-10">
                        <div class="flex items-center gap-2 mb-1">
                            <span class="text-[10px] text-zinc-300 border border-white/10 px-2 py-0.5 rounded-full tracking-wider font-bold">首爾</span>
                            <i data-lucide="cloud-sun" class="text-white/90" size="16"></i>
                        </div>
                        <div class="text-[11px] text-zinc-400 mt-1 font-bold">晴時多雲</div>
                    </div>
                    <div class="text-5xl font-bold text-white relative z-10 font-num">8°C</div>
                </div>

                <!-- Next Destination -->
                <div class="glass rounded-[2rem] p-6 col-span-2 border-l-2 border-l-yellow-600 relative overflow-hidden group active:scale-98 transition">
                    <div class="absolute right-0 top-0 bottom-0 w-32 bg-gradient-to-l from-black/50 to-transparent pointer-events-none"></div>
                    
                    <div class="flex flex-col justify-start mb-2 relative z-10">
                        <div class="flex items-center gap-3 mb-1">
                            <div class="text-[10px] uppercase tracking-[0.2em] text-zinc-500 font-bold whitespace-nowrap">下一站目的地</div>
                            <div id="dash-next-time" class="text-xs text-yellow-500 font-bold tracking-wider font-num"></div>
                        </div>
                        <h3 class="text-xl text-white font-bold truncate w-full" id="dash-next-event">載入中...</h3>
                    </div>
                    
                    <div class="flex gap-3 mt-3 relative z-10">
                         <button onclick="quickTaxi()" class="flex-1 bg-yellow-600/20 border border-yellow-600/50 text-yellow-500 text-xs py-2 rounded-xl flex items-center justify-center gap-1 font-black tracking-wider hover:bg-yellow-600 hover:text-black transition">
                            <i data-lucide="car-front" size="14"></i> TAXI
                         </button>
                         <button onclick="quickMap()" class="flex-1 bg-zinc-800 border border-zinc-700 text-zinc-300 text-xs py-2 rounded-xl flex items-center justify-center gap-1 tracking-wider hover:bg-zinc-700 transition font-bold">
                            <i data-lucide="map" size="14"></i> NAVER
                         </button>
                    </div>
                </div>

                <!-- Hotel Info (Unified Design) -->
                <div onclick="openNaverMap('Amanti Seoul Hotel')" class="glass rounded-[2rem] p-6 col-span-2 border-l-2 border-l-blue-500 relative overflow-hidden group active:scale-98 transition cursor-pointer">
                    <!-- Right Gradient Shadow (Blue for Hotel) -->
                    <div class="absolute right-0 top-0 bottom-0 w-32 bg-gradient-to-l from-blue-900/20 to-transparent pointer-events-none"></div>
                    
                    <div class="flex flex-col justify-start relative z-10">
                        <div class="flex items-center justify-between mb-1">
                            <div class="text-[10px] uppercase tracking-[0.2em] text-zinc-500 font-bold whitespace-nowrap">住宿飯店</div>
                        </div>
                        <h3 class="text-xl text-white font-bold truncate w-full font-serif">Amanti Seoul Hotel</h3>
                        <p class="text-xs text-zinc-400 mt-1 font-num tracking-wider">Mapo-gu, Seoul</p>
                    </div>
                    
                    <!-- Floating Icon for Hint -->
                    <div class="absolute right-6 top-1/2 -translate-y-1/2 text-zinc-600 group-hover:text-blue-400 transition">
                        <i data-lucide="map-pin" size="24"></i>
                    </div>
                </div>

                <!-- Tools Section -->
                <div class="col-span-2 mt-2">
                    <h3 class="text-sm text-zinc-400 mb-3 tracking-widest font-bold">在地工具</h3>
                    <div class="grid grid-cols-2 gap-3">
                        <a href="https://papago.naver.com/" target="_blank" class="glass p-4 rounded-2xl flex flex-col justify-center gap-2 group active:scale-95 transition border border-green-500/20 hover:bg-green-900/20">
                            <div class="flex items-center gap-2 text-green-400 font-bold"><i data-lucide="languages" size="18"></i> Papago</div>
                            <div class="text-[10px] text-zinc-500 font-bold">韓語翻譯神器</div>
                        </a>
                        <a href="http://www.seoulmetro.co.kr/en/cyberStation.do" target="_blank" class="glass p-4 rounded-2xl flex flex-col justify-center gap-2 group active:scale-95 transition border border-yellow-500/20 hover:bg-yellow-900/20">
                            <div class="flex items-center gap-2 text-yellow-500 font-bold"><i data-lucide="train" size="18"></i> Subway</div>
                            <div class="text-[10px] text-zinc-500 font-bold">地鐵路線圖</div>
                        </a>
                    </div>
                </div>

                <!-- Emergency -->
                <div class="glass p-5 rounded-[1.5rem] col-span-2">
                    <h3 class="text-sm text-zinc-400 mb-3 tracking-widest font-bold">緊急聯絡</h3>
                    <div class="flex gap-3">
                        <a href="tel:112" class="flex-1 bg-zinc-800 py-3 rounded-xl text-center text-xs text-zinc-300 hover:bg-zinc-700 font-bold border border-zinc-700">警察 112</a>
                        <a href="tel:119" class="flex-1 bg-zinc-800 py-3 rounded-xl text-center text-xs text-zinc-300 hover:bg-zinc-700 font-bold border border-zinc-700">救護 119</a>
                    </div>
                </div>
                
                <!-- Memo -->
                <div class="glass p-5 rounded-[1.5rem] col-span-2">
                    <h3 class="text-sm text-zinc-400 mb-3 tracking-widest font-bold">共用備忘錄</h3>
                    <textarea id="global-memo" class="w-full bg-zinc-900/50 border border-zinc-700 rounded-xl p-4 text-white text-sm h-32 focus:border-yellow-600 outline-none placeholder-zinc-700 font-bold" placeholder="預約代號、重要筆記..."></textarea>
                </div>
            </div>
            
            <div class="pb-24"></div>
        </div>

        <!-- 1. Itinerary -->
        <div id="view-itinerary" class="tab-content space-y-6">
            <h2 class="text-3xl font-bold text-white tracking-widest">行程規劃</h2>
            
            <div class="sticky top-0 z-10 glass rounded-2xl p-2 mx-[-6px] mb-4 backdrop-blur-xl">
                <div class="flex justify-between items-center px-1" id="date-tabs"></div>
            </div>
            
            <div id="itinerary-list" class="space-y-0 relative pl-4 pb-24">
                <div class="absolute left-[23px] top-2 bottom-2 w-[1px] bg-gradient-to-b from-transparent via-zinc-800 to-transparent"></div>
            </div>
        </div>

        <!-- 2. Packing -->
        <div id="view-packing" class="tab-content space-y-6">
            <h2 class="text-3xl font-bold text-white tracking-widest">行李籌備</h2>
            
            <div class="glass rounded-[2rem] p-6 flex items-center gap-6 border-t border-white/10">
                <div class="relative w-24 h-24 flex-shrink-0 flex items-center justify-center">
                    <svg class="transform -rotate-90 w-24 h-24">
                        <circle cx="48" cy="48" r="42" stroke="#1f1f1f" stroke-width="3" fill="transparent" />
                        <circle id="pack-ring" cx="48" cy="48" r="42" stroke="url(#grad1)" stroke-width="3" fill="transparent" stroke-dasharray="264" stroke-dashoffset="264" class="transition-all duration-1000 ease-out" stroke-linecap="round" />
                        <defs><linearGradient id="grad1"><stop offset="0%" stop-color="#b38728"/><stop offset="100%" stop-color="#fcf6ba"/></linearGradient></defs>
                    </svg>
                    <span id="pack-percent" class="absolute text-lg font-black text-white font-num">0%</span>
                </div>
                <div>
                    <div class="text-lg text-white font-bold tracking-wide">打包進度</div>
                    <div class="text-xs text-zinc-500 mt-1 leading-relaxed font-bold">確認護照、eSIM 與轉接頭。</div>
                </div>
            </div>
            <div id="packing-list" class="space-y-5 pb-24"></div>
        </div>

        <!-- 3. Expenses -->
        <div id="view-expenses" class="tab-content space-y-6">
            <h2 class="text-3xl font-bold text-white tracking-widest">懶人分帳</h2>
            
            <div class="w-full aspect-[1.7/1] rounded-[2rem] bg-gradient-to-bl from-[#1a1a1a] via-black to-[#0a0a0a] border border-white/10 p-7 relative overflow-hidden shadow-2xl flex flex-col justify-between">
                <div class="absolute -right-10 -top-10 w-48 h-48 bg-yellow-600/10 rounded-full blur-3xl"></div>
                <div class="flex justify-between items-start z-10">
                    <i data-lucide="nfc" class="text-zinc-600 rotate-90" size="28"></i>
                    <span class="text-[10px] text-yellow-600/90 tracking-[0.3em] border border-yellow-600/30 px-3 py-1 rounded font-bold font-num">TRIP CARD</span>
                </div>
                <div class="z-10 pl-1">
                    <div class="text-[10px] text-zinc-500 uppercase tracking-[0.2em] mb-2 font-bold">Total Expenses</div>
                    <div id="total-expense" class="text-4xl font-bold text-white tracking-tight text-shadow-sm font-num">NT$ 0</div>
                </div>
                <div class="flex justify-between items-end z-10">
                    <div class="text-[10px] text-zinc-500 tracking-[0.3em] font-bold font-num">**** 2026</div>
                    <div class="text-xs text-white/70 italic tracking-wider font-bold">Group Splitting</div>
                </div>
            </div>

            <div class="glass rounded-t-[2.5rem] min-h-[40vh] p-8 -mt-6 border-t border-white/5 relative z-0">
                <div class="w-12 h-1 bg-zinc-800 rounded-full mx-auto mb-8"></div>
                <div class="flex justify-between items-center mb-6">
                    <h3 class="text-sm font-bold text-zinc-300 tracking-wider">分帳明細</h3>
                    <button onclick="toggleSettlement()" class="text-[10px] text-yellow-600 uppercase tracking-wider hover:text-white transition bg-yellow-600/10 px-3 py-1 rounded-full font-bold">一鍵結算</button>
                </div>
                <div id="settlement-view" class="hidden mb-6 bg-[#0a0a0a] rounded-2xl p-5 border border-zinc-800 shadow-inner">
                    <div id="split-result" class="text-sm text-zinc-300 space-y-2 font-bold leading-loose text-center"></div>
                </div>
                <div id="expense-list" class="space-y-4 pb-24"></div>
            </div>
        </div>
    </main>

    <!-- Navigation Dock -->
    <nav class="fixed bottom-8 left-6 right-6 h-20 glass-dock rounded-[2.5rem] flex justify-between items-center px-6 z-40">
        <button onclick="switchTab('view-dashboard', this)" class="nav-btn text-yellow-500 transition-transform active:scale-90 flex flex-col items-center gap-1.5 w-12 group">
            <i data-lucide="layout-grid" size="22" class="group-hover:drop-shadow-[0_0_5px_rgba(212,175,55,0.8)]"></i>
            <span class="text-[9px] font-bold tracking-widest">首頁</span>
        </button>
        <button onclick="switchTab('view-itinerary', this)" class="nav-btn text-zinc-500 transition-transform active:scale-90 flex flex-col items-center gap-1.5 w-12 hover:text-zinc-300">
            <i data-lucide="calendar" size="22"></i>
            <span class="text-[9px] font-bold tracking-widest">行程</span>
        </button>
        <button onclick="openActionSheet()" class="btn-press -mt-10 w-16 h-16 bg-gradient-to-tr from-[#8a7020] via-[#D4AF37] to-[#F4E29F] rounded-[1.5rem] rotate-45 flex items-center justify-center shadow-[0_0_30px_rgba(212,175,55,0.3)] border border-white/20 z-50 transition-all hover:scale-105 active:scale-95">
            <i data-lucide="plus" class="text-black -rotate-45" size="32" stroke-width="2.5"></i>
        </button>
        <button onclick="switchTab('view-expenses', this)" class="nav-btn text-zinc-500 transition-transform active:scale-90 flex flex-col items-center gap-1.5 w-12 hover:text-zinc-300">
            <i data-lucide="credit-card" size="22"></i>
            <span class="text-[9px] font-bold tracking-widest">帳務</span>
        </button>
        <button onclick="switchTab('view-packing', this)" class="nav-btn text-zinc-500 transition-transform active:scale-90 flex flex-col items-center gap-1.5 w-12 hover:text-zinc-300">
            <i data-lucide="backpack" size="22"></i>
            <span class="text-[9px] font-bold tracking-widest">行李</span>
        </button>
    </nav>

    <!-- Taxi Mode & Action Sheet & Modals -->
    <div id="taxi-overlay" class="fixed inset-0 bg-black z-[100] hidden flex flex-col justify-center items-center p-8 text-center">
        <button onclick="closeTaxiMode()" class="absolute top-8 right-8 text-zinc-500 p-4"><i data-lucide="x" size="32"></i></button>
        <div class="text-yellow-600 text-sm tracking-[0.3em] font-black mb-8 animate-pulse">TAXI MODE</div>
        <div class="text-zinc-400 text-lg mb-2 font-kr font-bold">기사님, 여기로 가주세요</div>
        <div id="taxi-kor-title" class="text-white text-5xl font-black mb-6 font-kr leading-tight"></div>
        <div id="taxi-kor-addr" class="text-zinc-300 text-2xl font-kr font-bold leading-relaxed border-t border-zinc-800 pt-6 mt-2"></div>
        <div id="taxi-cht-title" class="text-zinc-600 text-sm mt-12 font-bold tracking-widest"></div>
    </div>

    <div id="action-sheet-overlay" class="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 hidden opacity-0 transition-opacity duration-300" onclick="closeActionSheet()"></div>
    <div id="action-sheet" class="fixed bottom-0 left-0 right-0 bg-[#0f0f0f] rounded-t-[3rem] p-8 z-50 transform translate-y-full transition-transform duration-300 border-t border-white/10 shadow-2xl">
        <div class="w-12 h-1.5 bg-zinc-800 rounded-full mx-auto mb-8"></div>
        <div class="grid grid-cols-3 gap-6 mb-8">
            <button onclick="window.openAddEvent()" class="flex flex-col items-center gap-3 p-5 bg-zinc-900/80 rounded-[1.5rem] border border-zinc-800 active:scale-95 transition">
                <div class="w-14 h-14 rounded-full bg-blue-900/20 text-blue-400 flex items-center justify-center"><i data-lucide="map-pin" size="24"></i></div>
                <span class="text-xs text-zinc-300 font-bold">新行程</span>
            </button>
            <button onclick="openSubModal('modal-expense')" class="flex flex-col items-center gap-3 p-5 bg-zinc-900/80 rounded-[1.5rem] border border-zinc-800 active:scale-95 transition">
                <div class="w-14 h-14 rounded-full bg-green-900/20 text-green-400 flex items-center justify-center"><i data-lucide="receipt" size="24"></i></div>
                <span class="text-xs text-zinc-300 font-bold">記一筆</span>
            </button>
            <button onclick="openSubModal('modal-packing')" class="flex flex-col items-center gap-3 p-5 bg-zinc-900/80 rounded-[1.5rem] border border-zinc-800 active:scale-95 transition">
                <div class="w-14 h-14 rounded-full bg-purple-900/20 text-purple-400 flex items-center justify-center"><i data-lucide="backpack" size="24"></i></div>
                <span class="text-xs text-zinc-300 font-bold">新增行李</span>
            </button>
        </div>
        <button onclick="closeActionSheet()" class="w-full py-4 text-zinc-500 text-sm tracking-widest font-bold">取消</button>
    </div>

    <!-- Modals -->
    <div id="modal-container" class="fixed inset-0 z-[60] hidden flex items-center justify-center px-5 bg-black/80 backdrop-blur-xl">
        <div id="modal-itinerary" class="hidden w-full max-w-sm glass rounded-[2rem] p-7 shadow-2xl slide-up max-h-[90vh] overflow-y-auto">
            <div class="flex justify-between items-center mb-6 border-b border-white/10 pb-4">
                <h3 id="modal-itinerary-title" class="text-xl text-white font-bold">新增行程</h3>
                <button id="btn-delete-event" onclick="deleteCurrentEvent()" class="text-red-500 hidden"><i data-lucide="trash-2" size="20"></i></button>
            </div>
            <div class="space-y-4">
                <div class="grid grid-cols-1 gap-3"> 
                    <div>
                        <label class="block text-xs text-zinc-500 mb-1 font-bold ml-1">日期</label>
                        <div class="w-full bg-zinc-900 border border-zinc-700 rounded-xl overflow-hidden flex items-center h-[56px]">
                            <input type="date" id="evt-date" class="block w-full h-full bg-transparent pl-4 pr-2 text-white font-bold z-10 relative">
                        </div>
                    </div>
                    <div>
                        <label class="block text-xs text-zinc-500 mb-1 font-bold ml-1">時間</label>
                        <div class="w-full bg-zinc-900 border border-zinc-700 rounded-xl overflow-hidden flex items-center h-[56px]">
                            <input type="time" id="evt-time" class="block w-full h-full bg-transparent pl-4 pr-12 text-white font-bold z-10 relative">
                        </div>
                    </div>
                </div>
                
                <input type="text" id="evt-title" placeholder="地點名稱 (中文)" class="w-full bg-zinc-900 border border-zinc-700 rounded-xl p-4 text-white outline-none placeholder-zinc-700 font-bold">
                <input type="text" id="evt-kor-title" placeholder="地點名稱 (韓文 - 用於計程車)" class="w-full bg-zinc-900 border border-zinc-700 rounded-xl p-4 text-white outline-none placeholder-zinc-700 font-bold">
                <input type="text" id="evt-kor-addr" placeholder="詳細地址 (韓文 - 用於導航)" class="w-full bg-zinc-900 border border-zinc-700 rounded-xl p-4 text-white outline-none placeholder-zinc-700 font-bold">
                <textarea id="evt-memo" placeholder="備忘錄 (預約號碼/低消...)" class="w-full bg-zinc-900 border border-zinc-700 rounded-xl p-4 text-white outline-none placeholder-zinc-700 h-24 font-bold"></textarea>
            </div>
            <div class="flex gap-4 mt-8">
                <button onclick="closeSubModal()" class="flex-1 py-3.5 rounded-xl bg-zinc-800 text-zinc-400 font-bold">取消</button>
                <button onclick="window.saveEvent()" class="flex-1 py-3.5 rounded-xl bg-yellow-600 text-black font-black">儲存</button>
            </div>
        </div>

        <div id="modal-expense" class="hidden w-full max-w-sm glass rounded-[2rem] p-7 shadow-2xl slide-up">
            <h3 class="text-xl text-white font-bold mb-6 border-b border-white/10 pb-4">新增支出</h3>
            <div class="space-y-4">
                <div>
                    <label class="block text-xs text-zinc-500 mb-1 font-bold ml-1">付款人</label>
                    <div class="relative">
                        <select id="exp-payer" class="w-full bg-zinc-900 border border-zinc-700 rounded-xl p-4 text-white outline-none font-bold appearance-none">
                            <!-- options populated by JS -->
                        </select>
                        <div class="absolute inset-y-0 right-0 flex items-center px-4 pointer-events-none text-zinc-500">
                            <i data-lucide="chevron-down" size="16"></i>
                        </div>
                    </div>
                </div>

                <div class="grid grid-cols-2 gap-3">
                    <div>
                        <label class="block text-xs text-zinc-500 mb-1 font-bold ml-1">韓幣 (KRW)</label>
                        <input type="number" id="exp-amount-krw" placeholder="₩" class="w-full bg-zinc-900 border border-zinc-700 rounded-xl p-4 text-white outline-none font-bold font-num" oninput="convertExpense('krw')">
                    </div>
                    <div>
                        <label class="block text-xs text-zinc-500 mb-1 font-bold ml-1">台幣 (TWD)</label>
                        <input type="number" id="exp-amount" placeholder="$" class="w-full bg-zinc-900 border border-zinc-700 rounded-xl p-4 text-white outline-none font-bold font-num" oninput="convertExpense('twd')">
                    </div>
                </div>
                <div class="text-[10px] text-zinc-500 text-right -mt-2 pr-1 font-num">匯率參考: 0.024</div>

                <input type="text" id="exp-desc" placeholder="項目 (例如: 午餐)" class="w-full bg-zinc-900 border border-zinc-700 rounded-xl p-4 text-white outline-none font-bold">
                <div class="bg-zinc-900/50 p-4 rounded-xl border border-zinc-700">
                    <label class="text-xs text-zinc-500 mb-2 block font-bold">分攤成員</label>
                    <div class="grid grid-cols-2 gap-2" id="exp-members"></div>
                </div>
            </div>
            <div class="flex gap-4 mt-8">
                <button onclick="closeSubModal()" class="flex-1 py-3.5 rounded-xl bg-zinc-800 text-zinc-400 font-bold">取消</button>
                <button onclick="window.addExpense()" class="flex-1 py-3.5 rounded-xl bg-yellow-600 text-black font-black">儲存</button>
            </div>
        </div>

        <div id="modal-packing" class="hidden w-full max-w-sm glass rounded-[2rem] p-7 shadow-2xl slide-up">
            <h3 class="text-xl text-white font-bold mb-6 border-b border-white/10 pb-4">新增行李</h3>
            <div class="space-y-4">
                <select id="pack-cat" class="w-full bg-zinc-900 border border-zinc-700 rounded-xl p-4 text-white outline-none font-bold">
                    <option value="證件金錢">證件金錢</option>
                    <option value="電子產品">電子產品</option>
                    <option value="衣物">衣物</option>
                    <option value="盥洗/藥品">盥洗/藥品</option>
                    <option value="其他">其他</option>
                </select>
                <input type="text" id="pack-item" placeholder="物品名稱" class="w-full bg-zinc-900 border border-zinc-700 rounded-xl p-4 text-white outline-none font-bold">
            </div>
            <div class="flex gap-4 mt-8">
                <button onclick="closeSubModal()" class="flex-1 py-3.5 rounded-xl bg-zinc-800 text-zinc-400 font-bold">取消</button>
                <button onclick="window.addPackItem()" class="flex-1 py-3.5 rounded-xl bg-yellow-600 text-black font-black">儲存</button>
            </div>
        </div>

        <div id="modal-members" class="hidden w-full max-w-sm glass rounded-[2rem] p-7 shadow-2xl slide-up">
            <h3 class="text-xl text-white font-bold mb-6 border-b border-white/10 pb-4">人員管理</h3>
            <div class="space-y-4">
                <div class="flex gap-2">
                    <input type="text" id="new-member-name" placeholder="輸入名字 (如: 小明)" class="flex-1 bg-zinc-900 border border-zinc-700 rounded-xl p-3 text-white outline-none font-bold">
                    <button onclick="window.addMember()" class="bg-yellow-600 text-black px-4 rounded-xl font-bold">新增</button>
                </div>
                <div id="members-list" class="space-y-2 max-h-48 overflow-y-auto"></div>
            </div>
            <div class="flex gap-4 mt-8">
                <button onclick="closeSubModal()" class="w-full py-3.5 rounded-xl bg-zinc-800 text-zinc-400 font-bold">關閉</button>
            </div>
        </div>
    </div>

    <!-- Firebase -->
    <script type="module">
        import { initializeApp } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-app.js";
        import { getFirestore, doc, setDoc, onSnapshot } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-firestore.js";
        import { getAuth, signInAnonymously } from "https://www.gstatic.com/firebasejs/10.8.0/firebase-auth.js";

        const firebaseConfig = {
            apiKey: "AIzaSyCnDWYi6jHu5ZJOSiAdLna_DCYTd1ro1wI",
            authDomain: "korea-0318.firebaseapp.com",
            projectId: "korea-0318",
            storageBucket: "korea-0318.firebasestorage.app",
            messagingSenderId: "723971661158",
            appId: "1:723971661158:web:28796c672f28c259b63ca7",
            measurementId: "G-DG9KCGR296"
        };

        const app = initializeApp(firebaseConfig);
        const db = getFirestore(app);
        const auth = getAuth(app);
        const TRIP_ID = "main_trip_data"; 

        const defaultData = {
            itinerary: { "2026-03-18": [], "2026-03-19": [], "2026-03-20": [], "2026-03-21": [], "2026-03-22": [] },
            packing: [
                {id: 1, cat: '證件金錢', name: '護照', checked: false},
                {id: 2, cat: '電子產品', name: '萬用轉接頭', checked: false}
            ],
            expenses: [],
            memo: "",
            members: ["我"]
        };

        let appData = defaultData;
        let currentDay = "2026-03-18";
        let editingContext = null;

        async function init() {
            try {
                await signInAnonymously(auth);
                onSnapshot(doc(db, "trips", TRIP_ID), (docSnap) => {
                    if (docSnap.exists()) {
                        appData = docSnap.data();
                    } else {
                        saveDataToFirebase();
                    }
                    renderAll();
                    document.getElementById('loading-screen').style.opacity = 0;
                    setTimeout(() => document.getElementById('loading-screen').style.display = 'none', 500);
                });
            } catch (error) {
                console.error("Firebase Error:", error);
                document.getElementById('loading-screen').style.display = 'none';
            }
        }

        async function saveDataToFirebase() {
            try { await setDoc(doc(db, "trips", TRIP_ID), appData); } catch (e) { console.error("Save failed: ", e); }
        }

        window.saveData = saveDataToFirebase;

        window.addMember = () => {
            const name = document.getElementById('new-member-name').value.trim();
            if(name && !appData.members.includes(name)) {
                appData.members.push(name);
                document.getElementById('new-member-name').value = '';
                saveDataToFirebase();
            }
        };

        // Set "Me" function
        window.setAsMe = (name) => {
            localStorage.setItem('korea_travel_me', name);
            updateDashboard();
            // Update UI feedback immediately
            window.renderMembers(); 
        };

        window.removeMember = (name) => {
            if(confirm(`確定移除 ${name}?`)) {
                appData.members = appData.members.filter(m => m !== name);
                saveDataToFirebase();
            }
        };

        window.saveEvent = () => {
            const date = document.getElementById('evt-date').value;
            const time = document.getElementById('evt-time').value;
            const title = document.getElementById('evt-title').value;
            const korTitle = document.getElementById('evt-kor-title').value;
            const korAddr = document.getElementById('evt-kor-addr').value;
            const memo = document.getElementById('evt-memo').value;

            if(date && time && title) {
                if (editingContext) {
                     appData.itinerary[editingContext.date].splice(editingContext.index, 1);
                }
                if (!appData.itinerary[date]) appData.itinerary[date] = [];

                appData.itinerary[date].push({time, title, korTitle, korAddr, memo});
                appData.itinerary[date].sort((a,b) => a.time.localeCompare(b.time));
                
                saveDataToFirebase();
                currentDay = date; 
                closeSubModal();
                renderItinerary(); 
            } else {
                alert("請填寫日期、時間和名稱");
            }
        };

        window.deleteCurrentEvent = () => {
            if(editingContext && confirm('確定要刪除此行程？')) {
                appData.itinerary[editingContext.date].splice(editingContext.index, 1);
                saveDataToFirebase();
                closeSubModal();
            }
        };
        
        window.openEditEvent = (index) => {
            const event = appData.itinerary[currentDay][index];
            if (!event) return;

            editingContext = { date: currentDay, index: index };
            
            document.getElementById('modal-itinerary-title').innerText = "編輯行程";
            document.getElementById('btn-delete-event').classList.remove('hidden');
            
            document.getElementById('evt-date').value = currentDay;
            document.getElementById('evt-time').value = event.time;
            document.getElementById('evt-title').value = event.title;
            document.getElementById('evt-kor-title').value = event.korTitle || "";
            document.getElementById('evt-kor-addr').value = event.korAddr || "";
            document.getElementById('evt-memo').value = event.memo || "";
            
            openSubModal('modal-itinerary', true); 
        };

        // Explicitly Open Add Event
        window.openAddEvent = () => {
            // Clear editing context
            editingContext = null;
            
            document.getElementById('modal-itinerary-title').innerText = "新增行程";
            document.getElementById('btn-delete-event').classList.add('hidden');
            
            // Force Clear Inputs
            document.getElementById('evt-date').value = currentDay;
            document.getElementById('evt-time').value = "";
            document.getElementById('evt-title').value = "";
            document.getElementById('evt-kor-title').value = "";
            document.getElementById('evt-kor-addr').value = "";
            document.getElementById('evt-memo').value = "";

            // Open with 'skipClear' because we just cleared it manually
            openSubModal('modal-itinerary', true);
        };

        window.deleteEvent = (i) => {
             if(confirm('刪除此行程？')) {
                appData.itinerary[currentDay].splice(i, 1);
                saveDataToFirebase();
            }
        };

        window.addExpense = () => {
            const payer = document.getElementById('exp-payer').value;
            const amount = document.getElementById('exp-amount').value;
            const desc = document.getElementById('exp-desc').value;
            const checkboxes = document.querySelectorAll('#exp-members input:checked');
            const selectedMembers = Array.from(checkboxes).map(cb => cb.value);
            if(payer && amount && selectedMembers.length > 0) {
                appData.expenses.push({payer, amount, desc, members: selectedMembers});
                saveDataToFirebase();
                closeSubModal();
            } else {
                alert("請填寫完整資訊並選擇分攤成員");
            }
        };

        window.deleteExp = (i) => {
            appData.expenses.splice(i, 1);
            saveDataToFirebase();
        };

        window.togglePack = (id) => {
            const item = appData.packing.find(i => i.id === id);
            if(item) { item.checked = !item.checked; saveDataToFirebase(); }
        };

        window.addPackItem = () => {
            const cat = document.getElementById('pack-cat').value;
            const name = document.getElementById('pack-item').value;
            if(name) {
                appData.packing.push({id: Date.now(), cat, name, checked: false});
                saveDataToFirebase();
                closeSubModal();
            }
        };

        window.deletePack = (id) => {
            appData.packing = appData.packing.filter(i => i.id !== id);
            saveDataToFirebase();
        };

        window.setDay = (d) => {
            currentDay = d;
            renderItinerary();
        };

        window.convertExpense = (source) => {
            const rate = 0.024; // 1 KRW = 0.024 TWD
            const krwEl = document.getElementById('exp-amount-krw');
            const twdEl = document.getElementById('exp-amount');
            
            if(source === 'krw') {
                const val = parseFloat(krwEl.value);
                if(!isNaN(val)) {
                    twdEl.value = Math.round(val * rate);
                } else {
                    twdEl.value = '';
                }
            } else {
                const val = parseFloat(twdEl.value);
                if(!isNaN(val)) {
                    krwEl.value = Math.round(val / rate);
                } else {
                    krwEl.value = '';
                }
            }
        }

        window.renderMembers = () => {
            const list = document.getElementById('members-list');
            const currentMe = localStorage.getItem('korea_travel_me');
            
            // Update small text in modal header
            const meDisplay = document.getElementById('current-me-display');
            if(meDisplay) meDisplay.innerText = currentMe ? `我是: ${currentMe}` : '尚未設定身分';

            if (list) {
                list.innerHTML = appData.members.map(m => `
                    <div class="flex justify-between items-center bg-zinc-800 p-3 rounded-lg border ${m === currentMe ? 'border-yellow-600' : 'border-transparent'}">
                        <div class="flex items-center gap-3">
                            <span class="text-white font-bold">${m}</span>
                            ${m !== currentMe ? `<button onclick="window.setAsMe('${m}')" class="text-xs bg-zinc-700 px-2 py-1 rounded text-zinc-300 hover:bg-yellow-600 hover:text-black transition">這是我</button>` : '<span class="text-xs text-yellow-500 font-bold"> (我)</span>'}
                        </div>
                        <button onclick="window.removeMember('${m}')" class="text-red-500"><i data-lucide="trash-2" size="16"></i></button>
                    </div>
                `).join('');
                lucide.createIcons();
            }
        }

        window.populatePayers = () => {
            const select = document.getElementById('exp-payer');
            if (select) {
                select.innerHTML = appData.members.map(m => `<option value="${m}">${m}</option>`).join('');
            }
        }

        window.populateMembers = () => {
            const container = document.getElementById('exp-members');
            if (container) {
                container.innerHTML = appData.members.map(m => `
                    <label class="flex items-center gap-2 bg-black/40 p-2 rounded cursor-pointer">
                        <input type="checkbox" value="${m}" checked class="accent-yellow-600">
                        <span class="text-xs text-zinc-300 font-bold">${m}</span>
                    </label>
                `).join('');
            }
        }

        window.updateDashboard = () => {
            // Get local user name
            const myName = localStorage.getItem('korea_travel_me');
            const greetingNameEl = document.getElementById('greeting-name');
            const greetingHintEl = document.getElementById('greeting-hint');
            
            if(greetingNameEl) {
                if(myName) {
                     greetingNameEl.innerText = myName;
                     if(greetingHintEl) greetingHintEl.classList.add('hidden');
                } else {
                     greetingNameEl.innerText = (appData.members && appData.members.length > 0 ? appData.members[0] : "旅人");
                     if(greetingHintEl) greetingHintEl.classList.remove('hidden');
                }
            }

            let next = null;
            let nextDate = ""; 
            if (appData.itinerary) {
                const dates = Object.keys(appData.itinerary).sort();
                for(let d of dates) {
                    if(appData.itinerary[d].length > 0) { 
                        next = appData.itinerary[d][0]; 
                        nextDate = d; 
                        break; 
                    }
                }
            }
            const nextEl = document.getElementById("dash-next-event");
            const nextTimeEl = document.getElementById("dash-next-time");
            
            if (nextEl) {
                if(next) {
                    nextEl.innerText = next.title;
                    nextEl.dataset.korAddr = next.korAddr || ""; 
                    nextEl.dataset.title = next.title;
                    nextEl.dataset.korTitle = next.korTitle || "";
                    
                    const datePart = nextDate.split('-').slice(1).join('/');
                    if(nextTimeEl) nextTimeEl.innerText = `${datePart} ${next.time}`;
                } else {
                    nextEl.innerText = "暫無行程";
                    if(nextTimeEl) nextTimeEl.innerText = "";
                }
            }
        };

        window.autoLink = (text) => {
            if(!text) return '';
            const phoneRegex = /(?:\+?(\d{1,3}))?[-. (]*(\d{2,4})[-. )]*(\d{3,4})[-. ]*(\d{4})/g;
            let safeText = text.replace(/&/g, "&amp;").replace(/</g, "&lt;").replace(/>/g, "&gt;");
            return safeText.replace(phoneRegex, (match) => {
                return `<a href="tel:${match.replace(/\D/g,'')}" class="text-yellow-500 underline decoration-yellow-500/50 hover:text-yellow-400 transition">${match}</a>`;
            });
        };

        window.renderItinerary = () => {
            const dateTabs = document.getElementById('date-tabs');
            if (dateTabs && appData.itinerary) {
                const sortedDates = Object.keys(appData.itinerary).sort();
                dateTabs.innerHTML = sortedDates.map(date => {
                    const day = date.split('-')[2];
                    const active = date === currentDay;
                    const style = active ? 'bg-yellow-600 text-black font-bold scale-105 shadow-lg' : 'bg-zinc-900 text-zinc-500 border border-zinc-700';
                    return `<button onclick="setDay('${date}')" class="transition-all duration-300 min-w-[3.5rem] h-14 rounded-[1.2rem] flex flex-col items-center justify-center gap-0.5 mx-1 ${style}">
                            <span class="text-[9px] tracking-widest opacity-80">3月</span><span class="text-lg leading-none font-bold font-num">${day}</span></button>`;
                }).join('');
            }

            const list = document.getElementById('itinerary-list');
            if (!list) return;
            const events = (appData.itinerary && appData.itinerary[currentDay]) ? appData.itinerary[currentDay] : [];
            if(events.length === 0) {
                list.innerHTML = `<div class="text-zinc-600 text-xs italic pl-8 pt-6 tracking-widest font-bold">本日尚無行程安排。</div>`;
                return;
            }
            list.innerHTML = events.map((e, i) => `
                <!-- Removed card onclick, editing is now exclusive to pencil icon -->
                <div class="relative pl-8 pb-8 group fade-in event-item" data-id="${i}">
                    <div class="absolute left-[19px] top-1.5 w-2.5 h-2.5 rounded-full bg-yellow-600 shadow-[0_0_10px_#D4AF37] z-10 ring-4 ring-[#050505]"></div>
                    <div class="glass rounded-[1.5rem] p-5 border border-white/5 relative overflow-hidden active:scale-[0.98] transition-transform">
                        <div class="flex justify-between items-start mb-2 relative z-10">
                            <span class="text-yellow-500 text-sm tracking-widest font-bold font-num">${e.time}</span>
                            <!-- Exclusive Edit Trigger -->
                            <button onclick="openEditEvent(${i})" class="text-zinc-500 hover:text-white transition cursor-pointer p-2 -mr-2">
                                <i data-lucide="pencil" size="16"></i>
                            </button>
                        </div>
                        <h3 class="text-white text-lg tracking-wide mb-1 font-bold relative z-10">${e.title}</h3>
                        ${e.korTitle ? `<div class="text-zinc-500 text-xs font-kr mb-2 font-bold">${e.korTitle}</div>` : ''}
                        ${e.memo ? `<div class="bg-black/30 p-3 rounded-lg text-zinc-300 text-sm leading-loose mb-3 border-l-2 border-zinc-700 whitespace-pre-wrap font-bold shadow-inner">${window.autoLink(e.memo)}</div>` : ''}
                        
                        <div class="flex gap-2 mt-3 relative z-10">
                             ${e.korTitle ? `
                             <button onclick="openTaxiMode('${e.title}', '${e.korTitle}', '${e.korAddr}')" class="flex-1 bg-yellow-600/10 border border-yellow-600/30 text-yellow-500 py-2 rounded-xl text-xs font-bold flex items-center justify-center gap-1 hover:bg-yellow-600 hover:text-black transition">
                                <i data-lucide="car-front" size="14"></i> TAXI
                             </button>` : ''}
                             <button onclick="openNaverMap('${e.korAddr || e.title}')" class="flex-1 bg-zinc-800 border border-zinc-700 text-zinc-300 py-2 rounded-xl text-xs flex items-center justify-center gap-1 hover:bg-zinc-700 transition font-bold">
                                <i data-lucide="map" size="14"></i> 導航
                             </button>
                        </div>
                    </div>
                </div>
            `).join('');
            lucide.createIcons();
            new Sortable(list, {
                animation: 150, delay: 200, delayOnTouchOnly: true,
                onEnd: function (evt) {
                    const movedItem = appData.itinerary[currentDay].splice(evt.oldIndex, 1)[0];
                    appData.itinerary[currentDay].splice(evt.newIndex, 0, movedItem);
                    saveDataToFirebase();
                },
            });
        };

        window.renderPacking = () => {
            const list = document.getElementById('packing-list');
            if (!list) return;
            const total = appData.packing ? appData.packing.length : 0;
            const checked = appData.packing ? appData.packing.filter(i => i.checked).length : 0;
            const pct = total === 0 ? 0 : Math.round((checked/total)*100);
            
            const packPercentEl = document.getElementById('pack-percent');
            if (packPercentEl) packPercentEl.innerText = `${pct}%`;
            
            // Fix: Update the ring stroke-dashoffset
            const packRing = document.getElementById('pack-ring');
            if(packRing) {
                const offset = 264 - (264 * pct / 100);
                packRing.style.strokeDashoffset = offset;
            }

            const cats = [...new Set((appData.packing || []).map(i => i.cat))];
            list.innerHTML = cats.map(cat => {
                const items = appData.packing.filter(i => i.cat === cat);
                const html = items.map(item => `
                    <div class="flex items-center justify-between py-3 border-b border-white/5 last:border-0 group ${item.checked ? 'opacity-30' : 'opacity-100'} transition-opacity duration-300">
                        <label class="flex items-center gap-4 cursor-pointer w-full">
                            <input type="checkbox" ${item.checked ? 'checked' : ''} onchange="togglePack(${item.id})" class="accent-yellow-600 w-5 h-5 bg-zinc-800 border-zinc-600 rounded">
                            <span class="${item.checked ? 'line-through' : ''} text-sm text-zinc-300 font-bold">${item.name}</span>
                        </label>
                        <button onclick="deletePack(${item.id})" class="text-zinc-600 hover:text-red-500"><i data-lucide="minus-circle" size="16"></i></button>
                    </div>
                `).join('');
                return `<div class="glass rounded-[1.5rem] p-6 mb-4"><h4 class="text-sm text-yellow-600 tracking-[0.3em] mb-3 font-bold border-l-2 border-yellow-600 pl-2">${cat}</h4><div>${html}</div></div>`;
            }).join('');
            lucide.createIcons();
        };

        window.renderExpenses = () => {
            const list = document.getElementById('expense-list');
            if (!list) return; 
            let total = 0;
            let balances = {}; 
            if (appData.members) { appData.members.forEach(m => balances[m] = 0); }
            const expenses = appData.expenses || [];
            list.innerHTML = expenses.map((e, i) => {
                total += Number(e.amount);
                const share = e.amount / (e.members ? e.members.length : 1);
                if(balances[e.payer] !== undefined) balances[e.payer] += Number(e.amount);
                if(e.members) { e.members.forEach(m => { if(balances[m] !== undefined) balances[m] -= share; }); }
                return `
                    <div class="flex justify-between items-center py-4 border-b border-white/5 last:border-0 hover:bg-white/5 px-2 rounded-lg transition">
                        <div class="flex items-center gap-3 flex-1 min-w-0 mr-2">
                            <div class="flex-shrink-0 w-9 h-9 rounded-full bg-zinc-800 flex items-center justify-center text-xs font-bold text-zinc-400 border border-zinc-700">${e.payer[0]}</div>
                            <div class="min-w-0">
                                <div class="text-zinc-200 text-sm font-bold truncate">${e.desc}</div>
                                <div class="text-[10px] text-zinc-500 mt-0.5 font-bold truncate">付款: ${e.payer} | 分攤: ${e.members ? e.members.join(', ') : ''}</div>
                            </div>
                        </div>
                        <div class="flex items-center gap-3 flex-shrink-0">
                            <!-- 強制套用 font-num -->
                            <div class="text-white text-sm font-bold font-num">NT$ ${Number(e.amount).toLocaleString()}</div>
                            <button onclick="deleteExp(${i})" class="text-zinc-700 hover:text-red-500"><i data-lucide="trash-2" size="14"></i></button>
                        </div>
                    </div>
                `;
            }).join('');
            lucide.createIcons();
            const totalExpenseEl = document.getElementById('total-expense');
            if (totalExpenseEl) totalExpenseEl.innerText = `NT$ ${total.toLocaleString()}`;
            let html = '';
            Object.keys(balances).forEach(p => {
                const val = Math.round(balances[p]);
                if(val > 0) html += `<div class="flex justify-between text-green-400/90 text-xs py-1 border-b border-zinc-800/50"><span class="font-bold">${p}</span><span class="font-bold font-num">應收 $${val}</span></div>`;
                else if(val < 0) html += `<div class="flex justify-between text-red-400/90 text-xs py-1 border-b border-zinc-800/50"><span class="font-bold">${p}</span><span class="font-bold font-num">應付 $${Math.abs(val)}</span></div>`;
            });
            const splitResultEl = document.getElementById('split-result');
            if (splitResultEl) { splitResultEl.innerHTML = html || "暫無帳務"; }
        };

        window.renderAll = () => {
            updateDashboard();
            renderItinerary();
            renderPacking();
            renderExpenses();
            renderMembers();
            const memoArea = document.getElementById('global-memo');
            if(memoArea && document.activeElement !== memoArea) {
                memoArea.value = appData.memo || "";
            }
        };

        init();
    </script>

    <!-- UI Scripts -->
    <script>
        function openTaxiMode(title, korTitle, korAddr) {
            document.getElementById('taxi-kor-title').innerText = korTitle || title;
            document.getElementById('taxi-kor-addr').innerText = korAddr || "地址未設定";
            document.getElementById('taxi-cht-title').innerText = title;
            document.getElementById('taxi-overlay').classList.remove('hidden');
            document.getElementById('taxi-overlay').classList.add('flex');
        }
        function closeTaxiMode() {
            document.getElementById('taxi-overlay').classList.add('hidden');
            document.getElementById('taxi-overlay').classList.remove('flex');
        }
        function openNaverMap(query) {
            if(!query) return;
            window.open(`https://map.naver.com/p/search/${encodeURIComponent(query)}`, '_blank');
        }
        function quickTaxi() {
            const el = document.getElementById("dash-next-event");
            if(el.innerText !== "暫無行程" && el.dataset.korTitle) {
                openTaxiMode(el.dataset.title, el.dataset.korTitle, el.dataset.korAddr);
            } else {
                alert("下一個行程沒有韓文資訊");
            }
        }
        function quickMap() {
            const el = document.getElementById("dash-next-event");
            if(el.innerText !== "暫無行程") {
                openNaverMap(el.dataset.korAddr || el.dataset.title);
            }
        }
        function switchTab(tabId, btn) {
            document.querySelectorAll('.tab-content').forEach(el => {
                if(el.id !== tabId) {
                    el.classList.remove('active');
                    setTimeout(() => { if(!el.classList.contains('active')) el.style.display = 'none'; }, 300);
                }
            });
            const target = document.getElementById(tabId);
            target.style.display = 'block';
            void target.offsetWidth; 
            target.classList.add('active');

            document.querySelectorAll('.nav-btn').forEach(el => {
                el.classList.remove('text-yellow-500');
                el.classList.add('text-zinc-500');
            });
            if(btn) {
                btn.classList.remove('text-zinc-500');
                btn.classList.add('text-yellow-500');
            }
            document.getElementById('main-container').scrollTo({ top: 0, behavior: 'smooth' });
        }
        function toggleSettlement() { document.getElementById('settlement-view').classList.toggle('hidden'); }
        
        function openActionSheet() {
            const sheet = document.getElementById('action-sheet');
            const overlay = document.getElementById('action-sheet-overlay');
            overlay.classList.remove('hidden');
            void overlay.offsetWidth;
            overlay.classList.remove('opacity-0');
            sheet.classList.remove('translate-y-full');
        }
        function closeActionSheet() {
            const sheet = document.getElementById('action-sheet');
            const overlay = document.getElementById('action-sheet-overlay');
            sheet.classList.add('translate-y-full');
            overlay.classList.add('opacity-0');
            setTimeout(() => overlay.classList.add('hidden'), 300);
        }
        function openSubModal(id, skipClear) {
            closeActionSheet();
            if (!skipClear) { // Only clear if it's a fresh "Add" action
                if(id === 'modal-expense') {
                    window.populateMembers();
                    window.populatePayers(); // Populate dropdown
                }
                if(id === 'modal-members') window.renderMembers();
            }
            
            // For Edit Mode, we populate data before calling openSubModal(..., true)
            setTimeout(() => {
                document.getElementById('modal-container').classList.remove('hidden');
                document.querySelectorAll('#modal-container > div').forEach(d => d.classList.add('hidden'));
                document.getElementById(id).classList.remove('hidden');
            }, 300);
        }
        function closeSubModal() { document.getElementById('modal-container').classList.add('hidden'); }
    </script>
</body>
</html>


