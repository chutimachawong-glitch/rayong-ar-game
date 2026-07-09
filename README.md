<!doctype html>
<html lang="th">
 <head><script>window["__codeletBootstrap__"]=JSON.parse('{"A":"A","B":"20260709-05-e5cead5"}');</script><script src="/_sdk/f432b76fb310b513.telemetry_sdk.js" integrity="sha512-9FJQ55EKmmqhyyik8BhrMVfm0+iYYfb8uOlRsjtkxJMEI97qOVEI4PnHohDjQAtvAep0IOEpdQ64eki0sz62ug=="></script>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Rayong AR Time Travel</title>
  <script src="https://cdn.tailwindcss.com/3.4.17"></script>
  <script src="https://cdn.jsdelivr.net/npm/lucide@0.263.0/dist/umd/lucide.min.js"></script>
  <link href="https://fonts.googleapis.com/css2?family=Fredoka:wght@400;500;600;700&amp;display=swap" rel="stylesheet">
  <style>
  body { font-family: 'Fredoka', sans-serif; }
  .screen { display: none; }
  .screen.active { display: block; }
  .answer-btn { transition: transform .15s ease, box-shadow .15s ease; }
  .answer-btn:hover { transform: translateY(-4px); }
  .answer-btn:active { transform: scale(.97); }
  .pop-in { animation: popIn .4s ease; }
  @keyframes popIn { from { transform: scale(.8); opacity: 0 } to { transform: scale(1); opacity: 1 } }
  .float { animation: float 3s ease-in-out infinite; }
  @keyframes float { 0%,100% { transform: translateY(0) } 50% { transform: translateY(-10px) } }
  .feedback-pop { animation: fbPop .5s ease; }
  @keyframes fbPop { 0% { transform: scale(0) } 60% { transform: scale(1.15) } 100% { transform: scale(1) } }
  .cert-border { border: 10px double #f59e0b; }
  /* การ์ดความรู้ AR ที่ซ้อนบนกล้อง */
  .ar-card-anim { animation: arCard .5s ease; }
  @keyframes arCard { from { transform: translateY(12px) scale(.95); opacity: 0 } to { transform: translateY(0) scale(1); opacity: 1 } }
  :focus-visible { outline: 3px solid #f59e0b; outline-offset: 2px; }
</style>
  <script src="/_sdk/719055fef2a85d14.editing_sdk.js" integrity="sha512-kFqrdGgIiTOsu307feB5Cy3JVP9IayftsmCIZ0csxYBGuBmJQPhyvcnmKR8F0fTW97h5s1gAvz3SumI8zJ6OxQ=="></script>
  <script src="/_sdk/0179d719c431a79e.data_sdk.js" type="text/javascript" integrity="sha512-OsRvJkI5GkC3MJQcgotQYotpzrMSX415GiKKgvYdxQEEkzD/fdchShO2FMSy0PJr/tiINMXOk5Vl2zAgg6bUiA=="></script>
  <script src="/_sdk/9432170dbd2ae0df.resizing_sdk.js" type="text/javascript" integrity="sha512-FeT+58sb1f9ejWPWFjCbJvTT+SDwGV+ngrHUnlO7TWEOoqwOLj6p256kO3vOL7DIWl1cIgrobiof8v2bOigwPg=="></script>
 </head>
 <body data-template-id="__page-root" class="min-h-screen w-full text-slate-800"><!-- ================= หน้าแรก ================= -->
  <section id="screen-home" class="screen active min-h-screen w-full">
   <div class="relative min-h-screen w-full overflow-hidden"><img data-template-id="home-bg" class="canva-image absolute inset-0 w-full h-full object-cover" loading="lazy">
    <div class="absolute inset-0" style="background:linear-gradient(135deg, rgba(8,47,73,0.6), rgba(30,58,138,0.45))"></div>
    <main class="relative z-10 max-w-3xl mx-auto px-5 py-10 flex flex-col items-center text-center min-h-screen justify-center">
     <div class="text-5xl mb-2 float">
      🌊🍍🐟🏝️🏺⚔️
     </div>
     <h1 data-template-id="game-title" class="canva-text font-bold drop-shadow-lg text-white"></h1>
     <p data-template-id="game-tagline" class="canva-text mt-3 mb-8 drop-shadow text-white"></p>
     <div class="grid grid-cols-5 gap-2 w-full max-w-xl mb-8"><img data-template-id="stage1-img" class="canva-image w-full h-16 md:h-20 object-cover rounded-xl border-4 border-white/70 shadow hover:scale-105 transition-transform" loading="lazy"> <img data-template-id="stage2-img" class="canva-image w-full h-16 md:h-20 object-cover rounded-xl border-4 border-white/70 shadow hover:scale-105 transition-transform" loading="lazy"> <img data-template-id="stage3-img" class="canva-image w-full h-16 md:h-20 object-cover rounded-xl border-4 border-white/70 shadow hover:scale-105 transition-transform" loading="lazy"> <img data-template-id="stage4-img" class="canva-image w-full h-16 md:h-20 object-cover rounded-xl border-4 border-white/70 shadow hover:scale-105 transition-transform" loading="lazy"> <img data-template-id="stage5-img" class="canva-image w-full h-16 md:h-20 object-cover rounded-xl border-4 border-white/70 shadow hover:scale-105 transition-transform" loading="lazy">
     </div>
     <div class="flex flex-col gap-3 w-full max-w-xs"><button data-template-id="btn-start" class="canva-button rounded-2xl px-6 py-4 shadow-lg answer-btn text-white font-bold" onclick="startGame()"></button> <button data-template-id="btn-how" class="canva-button rounded-2xl px-6 py-4 shadow-lg answer-btn text-white font-bold" onclick="showScreen('how')"></button> <button data-template-id="btn-camera-toggle" class="canva-button rounded-2xl px-6 py-4 shadow-lg answer-btn text-white font-bold" onclick="toggleCamera()"></button>
      <p data-template-id="camera-status" id="camera-status-home" class="canva-text mt-1 text-yellow-300 font-medium drop-shadow"></p>
     </div>
    </main>
   </div>
  </section><!-- ================= หน้าวิธีเล่น ================= -->
  <section id="screen-how" class="screen min-h-screen w-full relative"><img data-template-id="how-bg" class="canva-image absolute inset-0 w-full h-full object-cover" loading="lazy">
   <div class="absolute inset-0" style="background:rgba(255,255,255,0.75)"></div>
   <main class="relative z-10 max-w-2xl mx-auto px-5 py-12">
    <div class="canva-card rounded-3xl p-6 md:p-8 shadow-xl bg-white/95 border border-amber-200">
     <h2 data-template-id="how-title" class="canva-text font-bold text-center mb-6"></h2>
     <ul class="space-y-4 text-lg">
      <li class="flex gap-3 items-start"><span class="text-2xl">📖</span><span data-template-id="how-step-1" class="canva-text"></span></li>
      <li class="flex gap-3 items-start"><span class="text-2xl">📷</span><span data-template-id="how-step-2" class="canva-text"></span></li>
      <li class="flex gap-3 items-start"><span class="text-2xl">👉</span><span data-template-id="how-step-3" class="canva-text"></span></li>
      <li class="flex gap-3 items-start"><span class="text-2xl">⭐</span><span data-template-id="how-step-4" class="canva-text"></span></li>
      <li class="flex gap-3 items-start"><span class="text-2xl">🏆</span><span data-template-id="how-step-5" class="canva-text"></span></li>
     </ul><button data-template-id="how-back" class="canva-button w-full mt-8 rounded-2xl px-6 py-4 shadow answer-btn text-white font-bold" onclick="showScreen('home')"></button>
    </div>
   </main>
  </section><!-- ================= หน้าเล่นเกม ================= -->
  <section id="screen-play" class="screen min-h-screen w-full relative py-5"><img id="play-bg-image" data-template-id="play-bg-default" class="canva-image absolute inset-0 w-full h-full object-cover transition-all duration-700" loading="lazy">
   <div class="absolute inset-0 bg-slate-900/40"></div>
   <main class="relative z-10 max-w-4xl mx-auto px-4"><!-- แถบสถานะ -->
    <div class="flex flex-wrap gap-2 justify-between items-center mb-4">
     <div class="canva-tag rounded-full px-4 py-2 shadow bg-white/95 font-semibold text-sm md:text-base border border-slate-200 text-slate-800">
      🏁 <span id="stage-label"></span>
     </div>
     <div class="flex gap-2">
      <div class="rounded-full px-4 py-2 shadow bg-yellow-300 text-slate-900 font-bold text-sm md:text-base border border-yellow-400">
       ⭐ <span id="score-val">0</span>
      </div>
      <div class="rounded-full px-4 py-2 shadow bg-sky-200 text-slate-900 font-bold text-sm md:text-base border border-sky-300">
       📋 <span id="qnum-val">1</span>/25
      </div>
      <div class="rounded-full px-4 py-2 shadow bg-red-200 text-slate-900 font-bold text-sm md:text-base border border-red-300">
       ⏰ <span id="time-val">90</span>
      </div>
     </div>
    </div><!-- โซนกล้อง AR ซ้อนภาพความรู้ -->
    <div class="canva-card rounded-3xl p-3 shadow-xl bg-white/95 mb-4 border-2 border-sky-100">
     <div id="ar-stage" class="relative w-full aspect-video bg-slate-800 rounded-2xl overflow-hidden flex items-center justify-center">
      <video id="webcam" autoplay playsinline muted class="w-full h-full object-cover hidden"></video><!-- ฉากหลังจำลองเมื่อกล้องปิด -->
      <div id="ar-fallback" class="absolute inset-0 flex flex-col items-center justify-center text-center text-white/90 p-4" style="background:radial-gradient(circle at 50% 30%, #0ea5e9, #082f49)"><i data-lucide="scan-line" class="w-10 h-10 mb-2 opacity-80"></i>
       <p data-template-id="camera-placeholder" id="camera-placeholder" class="canva-text text-sm font-medium mb-1"></p><button data-template-id="btn-req-cam" class="text-xs underline font-bold mt-1 cursor-pointer" onclick="toggleCamera()"></button>
      </div><!-- การ์ดความรู้ AR ซ้อนบนกล้อง (JS ใส่เนื้อหา) -->
      <div id="ar-knowledge" class="absolute left-1/2 bottom-3 -translate-x-1/2 w-[92%] max-w-md pointer-events-none">
       <div class="ar-card-anim rounded-2xl px-4 py-3 shadow-2xl backdrop-blur bg-white/85 border-2 border-amber-300 text-center">
        <div id="ar-emoji" class="text-4xl mb-1"></div>
        <p id="ar-fact" class="text-sm md:text-base font-semibold text-slate-800 leading-snug"></p>
       </div>
      </div>
     </div>
    </div><!-- คำถาม -->
    <div class="canva-card rounded-3xl p-5 md:p-7 shadow-xl bg-white/95 text-center mb-4 border-2 border-sky-100">
     <p id="question-text" class="text-xl md:text-2xl font-bold leading-snug text-slate-800"></p>
    </div><!-- คำตอบซ้าย/ขวา -->
    <div class="grid grid-cols-2 gap-3 md:gap-5 mb-4"><button id="answer-left" class="answer-btn rounded-3xl px-4 py-8 md:py-12 shadow-lg text-white text-xl md:text-2xl font-bold border-b-8 border-sky-700" style="background:linear-gradient(135deg,#0ea5e9,#0284c7)" onclick="choose('left')">
      <div class="text-3xl mb-2">
       👈
      </div><span id="answer-left-text"></span> </button> <button id="answer-right" class="answer-btn rounded-3xl px-4 py-8 md:py-12 shadow-lg text-white text-xl md:text-2xl font-bold border-b-8 border-green-700" style="background:linear-gradient(135deg,#22c55e,#16a34a)" onclick="choose('right')">
      <div class="text-3xl mb-2">
       👉
      </div><span id="answer-right-text"></span> </button>
    </div><!-- ข้อความแจ้งผล -->
    <div class="text-center h-12 mb-3"><span data-template-id="feedback-correct" id="feedback-correct" class="canva-text hidden feedback-pop inline-block font-bold text-2xl drop-shadow"></span> <span data-template-id="feedback-wrong" id="feedback-wrong" class="canva-text hidden feedback-pop inline-block font-bold text-2xl drop-shadow"></span>
    </div><!-- ปุ่มควบคุม -->
    <div class="flex gap-3"><button data-template-id="btn-pause" id="btn-pause" class="canva-button flex-1 rounded-2xl px-4 py-3 shadow answer-btn text-white font-bold" onclick="togglePause()"></button> <button data-template-id="btn-quit" class="canva-button flex-1 rounded-2xl px-4 py-3 shadow answer-btn text-white font-bold" onclick="quitGame()"></button>
    </div>
   </main>
  </section><!-- ================= หน้าสรุปผล ================= -->
  <section id="screen-result" class="screen min-h-screen w-full relative py-8"><img data-template-id="result-bg" class="canva-image absolute inset-0 w-full h-full object-cover" loading="lazy">
   <div class="absolute inset-0 bg-sky-950/40"></div>
   <main class="relative z-10 max-w-xl mx-auto px-5">
    <div class="canva-card rounded-3xl p-6 md:p-8 shadow-xl bg-white/95 text-center pop-in border border-sky-100">
     <div class="text-6xl mb-2">
      🎉
     </div>
     <h2 data-template-id="result-title" class="canva-text font-bold mb-4"></h2>
     <div class="grid grid-cols-2 gap-3 mb-5">
      <div class="rounded-2xl bg-yellow-50 p-4 border border-yellow-100">
       <p data-template-id="result-score-label" class="canva-text text-sm font-medium"></p>
       <p class="text-3xl font-bold text-amber-600"><span id="result-score">0</span></p>
      </div>
      <div class="rounded-2xl bg-sky-50 p-4 border border-sky-100">
       <p data-template-id="result-correct-label" class="canva-text text-sm font-medium"></p>
       <p class="text-3xl font-bold text-sky-600"><span id="result-correct">0</span>/25</p>
      </div>
     </div>
     <div id="result-reward-status" class="mb-4 p-3 rounded-2xl bg-slate-50 text-slate-700 font-bold border"></div>
     <p data-template-id="result-badge-label" class="canva-text font-bold mb-2"></p>
     <div id="badge-list" class="flex flex-wrap gap-2 justify-center mb-6"></div>
     <div class="flex flex-col gap-3"><button data-template-id="btn-view-cert" id="btn-view-cert" class="canva-button rounded-2xl px-6 py-4 shadow answer-btn text-white font-bold" onclick="showScreen('cert')"></button> <button data-template-id="btn-replay" class="canva-button rounded-2xl px-6 py-4 shadow answer-btn text-white font-bold" onclick="startGame()"></button> <button data-template-id="btn-result-home" class="canva-button rounded-2xl px-6 py-4 shadow answer-btn text-white font-bold" onclick="showScreen('home')"></button>
     </div>
    </div>
   </main>
  </section><!-- ================= หน้าใบประกาศ ================= -->
  <section id="screen-cert" class="screen min-h-screen w-full relative py-8"><img data-template-id="cert-bg-img" class="canva-image absolute inset-0 w-full h-full object-cover" loading="lazy">
   <div class="absolute inset-0 bg-amber-950/20"></div>
   <main class="relative z-10 max-w-2xl mx-auto px-5">
    <div class="cert-border rounded-3xl p-6 md:p-10 shadow-2xl bg-white text-center pop-in">
     <div class="text-5xl mb-3">
      🏅
     </div>
     <h2 data-template-id="cert-title" class="canva-text font-bold mb-4 text-amber-700"></h2>
     <p data-template-id="cert-body" class="canva-text text-lg leading-relaxed mb-4 text-slate-700"></p>
     <p class="text-4xl mb-4">🌊🍍🐟🏝️</p>
     <p data-template-id="cert-sign" class="canva-text text-sm text-slate-500 mb-6"></p><button data-template-id="btn-cert-home" class="canva-button rounded-2xl px-6 py-4 shadow answer-btn text-white" onclick="showScreen('home')"></button>
    </div>
   </main>
  </section>
  <script>
lucide.createIcons();

/* ================= ภาพพื้นหลังไดนามิกของแต่ละด่าน ================= */
const stageBackgrounds = { 1:"stage1-img", 2:"stage2-img", 3:"stage3-img", 4:"stage4-img", 5:"stage5-img" };

/* ================= การ์ดความรู้ AR ประจำแต่ละด่าน ================= */
const arFacts = {
  1: { emoji:"🏺⛵", text:"ระยองในอดีตเป็นเมืองประมงริมทะเลอ่าวไทย ผู้คนใช้เรือไม้ออกหาปลาและค้าขายทางทะเล" },
  2: { emoji:"⚔️🐎", text:"สมเด็จพระเจ้าตากสินมหาราชเคยยกทัพผ่านเมืองระยองเพื่อรวบรวมไพร่พลกอบกู้เอกราชไทย" },
  3: { emoji:"🐟🌴", text:"วิถีชีวิตชาวระยองผูกพันกับทะเลและสวนผลไม้ ตลาดสดเต็มไปด้วยอาหารทะเลและผลไม้สด" },
  4: { emoji:"🍈🍍", text:"ของดีเมืองระยองคือทุเรียน มังคุด เงาะ สับปะรด และอาหารทะเลสด ๆ อร่อยเลื่องชื่อ" },
  5: { emoji:"🏝️🏭", text:"ระยองปัจจุบันเป็นเมืองท่องเที่ยว (เกาะเสม็ด) และอุตสาหกรรมสำคัญของประเทศ" }
};

/* ================= คำถาม 25 ข้อ (5 ด่าน) ================= */
const questions = [
  { stage:1, stageName:"ด่าน 1 ระยองในอดีต 🏺", question:"ในอดีตระยองมีความสำคัญด้านใด?", left:"การค้าทางทะเล", right:"การค้าทางอากาศ", answer:"left" },
  { stage:1, stageName:"ด่าน 1 ระยองในอดีต 🏺", question:"ชาวระยองในอดีตส่วนใหญ่ทำอาชีพอะไร?", left:"ประมงและเกษตร", right:"ทำเหมืองถ่านหิน", answer:"left" },
  { stage:1, stageName:"ด่าน 1 ระยองในอดีต 🏺", question:"ระยองตั้งอยู่ติดกับอะไร?", left:"แม่น้ำโขง", right:"ทะเลอ่าวไทย", answer:"right" },
  { stage:1, stageName:"ด่าน 1 ระยองในอดีต 🏺", question:"เรือชาวประมงในอดีตทำจากอะไรเป็นหลัก?", left:"ไม้", right:"พลาสติก", answer:"left" },
  { stage:1, stageName:"ด่าน 1 ระยองในอดีต 🏺", question:"สินค้าจากทะเลที่ระยองมีมากคืออะไร?", left:"เกลือหิมะ", right:"อาหารทะเล", answer:"right" },

  { stage:2, stageName:"ด่าน 2 ตามรอยพระเจ้าตากสิน ⚔️", question:"พระเจ้าตากสินเคยยกทัพผ่านระยองหรือไม่?", left:"เคย", right:"ไม่เคย", answer:"left" },
  { stage:2, stageName:"ด่าน 2 ตามรอยพระเจ้าตากสิน ⚔️", question:"สมเด็จพระเจ้าตากสินทรงเป็นวีรกษัตริย์ผู้ทำอะไร?", left:"กู้เอกราชไทย", right:"สร้างรถไฟ", answer:"left" },
  { stage:2, stageName:"ด่าน 2 ตามรอยพระเจ้าตากสิน ⚔️", question:"พระองค์ทรงรวบรวมไพร่พลเพื่ออะไร?", left:"ท่องเที่ยว", right:"กอบกู้บ้านเมือง", answer:"right" },
  { stage:2, stageName:"ด่าน 2 ตามรอยพระเจ้าตากสิน ⚔️", question:"ระยองมีสถานที่รำลึกถึงพระเจ้าตากสินหรือไม่?", left:"มี", right:"ไม่มี", answer:"left" },
  { stage:2, stageName:"ด่าน 2 ตามรอยพระเจ้าตากสิน ⚔️", question:"เราควรมีคุณธรรมใดตามแบบพระเจ้าตากสิน?", left:"ความโลภ", right:"ความกล้าหาญ", answer:"right" },

  { stage:3, stageName:"ด่าน 3 วิถีชีวิตชาวระยอง 🐟", question:"ชาวประมงระยองออกเรือเพื่ออะไร?", left:"จับปลา", right:"เล่นสไลเดอร์", answer:"left" },
  { stage:3, stageName:"ด่าน 3 วิถีชีวิตชาวระยอง 🐟", question:"ตลาดสดของชาวระยองขายอะไรมาก?", left:"ข้าวสารพัดชนิด", right:"อาหารทะเลและผลไม้", answer:"right" },
  { stage:3, stageName:"ด่าน 3 วิถีชีวิตชาวระยอง 🐟", question:"ของกินขึ้นชื่อที่ทำจากปลาคืออะไร?", left:"น้ำปลาระยอง", right:"ไอศกรีม", answer:"left" },
  { stage:3, stageName:"ด่าน 3 วิถีชีวิตชาวระยอง 🐟", question:"ชาวสวนระยองปลูกต้นอะไรกันมาก?", left:"ต้นสน", right:"ต้นทุเรียนและผลไม้", answer:"right" },
  { stage:3, stageName:"ด่าน 3 วิถีชีวิตชาวระยอง 🐟", question:"วิถีชีวิตชาวระยองผูกพันกับสิ่งใด?", left:"ทะเลและสวน", right:"เทือกเขาสูงชัน", answer:"left" },

  { stage:4, stageName:"ด่าน 4 ของดีเมืองระยอง 🍍", question:"ผลไม้ราชาของระยองคืออะไร?", left:"แอปเปิล", right:"ทุเรียน", answer:"right" },
  { stage:4, stageName:"ด่าน 4 ของดีเมืองระยอง 🍍", question:"ผลไม้เมืองร้อนที่ระยองมีชื่อเสียงคืออะไร?", left:"สับปะรด", right:"สตรอว์เบอร์รี่", answer:"left" },
  { stage:4, stageName:"ด่าน 4 ของดีเมืองระยอง 🍍", question:"อาหารทะเลของดีเมืองระยองคืออะไร?", left:"กุ้ง หอย ปู ปลา", right:"เนื้อแกะแช่แข็ง", answer:"left" },
  { stage:4, stageName:"ด่าน 4 ของดีเมืองระยอง 🍍", question:"ผลไม้เปลือกแดงหนามงอนของระยองคืออะไร?", left:"เงาะ", right:"มะพร้าวน้ำหอม", answer:"left" },
  { stage:4, stageName:"ด่าน 4 ของดีเมืองระยอง 🍍", question:"ของฝากทะเลตากแห้งเรียกว่าอะไร?", left:"ลูกอม", right:"อาหารทะเลแปรรูป", answer:"right" },

  { stage:5, stageName:"ด่าน 5 ระยองปัจจุบัน 🏝️", question:"ปัจจุบันระยองเป็นแหล่งใดที่สำคัญ?", left:"อุตสาหกรรมและท่องเที่ยว", right:"เกษตรกรรมภูเขาไฟ", answer:"left" },
  { stage:5, stageName:"ด่าน 5 ระยองปัจจุบัน 🏝️", question:"เกาะเสม็ดเป็นสถานที่ท่องเที่ยวประเภทใด?", left:"น้ำตกและขุนเขา", right:"ชายหาดทะเล", answer:"right" },
  { stage:5, stageName:"ด่าน 5 ระยองปัจจุบัน 🏝️", question:"เราควรช่วยกันดูแลทะเลระยองอย่างไร?", left:"ทิ้งขยะลงทะเล", right:"ไม่ทิ้งขยะและรักษาความสะอาด", answer:"right" },
  { stage:5, stageName:"ด่าน 5 ระยองปัจจุบัน 🏝️", question:"ระยองมีท่าเรือสำคัญเพื่ออะไร?", left:"ขนส่งและการค้า", right:"จอดเรือยอชท์หรู", answer:"left" },
  { stage:5, stageName:"ด่าน 5 ระยองปัจจุบัน 🏝️", question:"เด็ก ๆ ควรภูมิใจในเมืองระยองหรือไม่?", left:"ควรภูมิใจ", right:"ไม่ควร", answer:"left" }
];

const badges = ["🏺 นักสำรวจอดีต","⚔️ ผู้กล้าแห่งระยอง","🐟 ผู้รู้วิถีชุมชน","🍍 นักชิมเมืองระยอง","🌟 นักพัฒนาอนาคต"];

/* ================= สถานะเกม ================= */
let current = 0, score = 0, correctCount = 0, earnedBadges = [];
let timeLeft = 90, timer = null, paused = false, locked = false, allCleared = false;

function showScreen(name){
  document.querySelectorAll('.screen').forEach(s=>s.classList.remove('active'));
  document.getElementById('screen-'+name).classList.add('active');
  window.scrollTo(0,0);
}

function startGame(){
  current=0; score=0; correctCount=0; earnedBadges=[]; timeLeft=90; paused=false; locked=false; allCleared=false;
  document.getElementById('score-val').textContent='0';
  document.getElementById('btn-pause').style.opacity='1';
  showScreen('play');
  renderQuestion();
  startTimer();
}

function startTimer(){
  clearInterval(timer);
  document.getElementById('time-val').textContent=timeLeft;
  timer=setInterval(()=>{
    if(paused) return;
    timeLeft--;
    document.getElementById('time-val').textContent=timeLeft;
    if(timeLeft<=0){ clearInterval(timer); finishGame(); }
  },1000);
}

function renderQuestion(){
  const q=questions[current];
  document.getElementById('stage-label').textContent=q.stageName;
  document.getElementById('question-text').textContent=q.question;
  document.getElementById('answer-left-text').textContent=q.left;
  document.getElementById('answer-right-text').textContent=q.right;
  document.getElementById('qnum-val').textContent=(current+1);

  // ภาพพื้นหลังไดนามิกตามด่าน (ผ่านการเปลี่ยน template id + refresh SDK)
  const bgImgElement = document.getElementById('play-bg-image');
  if (bgImgElement) {
    bgImgElement.setAttribute('data-template-id', stageBackgrounds[q.stage]);
    if (window.editingSdk && typeof window.editingSdk.refresh === 'function') {
      window.editingSdk.refresh();
    }
  }

  // การ์ดความรู้ AR ซ้อนบนกล้อง (เนื้อหา application ใน JS)
  const fact = arFacts[q.stage];
  const emojiEl = document.getElementById('ar-emoji');
  const factEl = document.getElementById('ar-fact');
  const cardWrap = document.querySelector('#ar-knowledge .ar-card-anim');
  if (emojiEl && factEl) {
    emojiEl.textContent = fact.emoji;
    factEl.textContent = fact.text;
    if (cardWrap){ cardWrap.classList.remove('ar-card-anim'); void cardWrap.offsetWidth; cardWrap.classList.add('ar-card-anim'); }
  }

  hideFeedback();
  locked=false;
}

function hideFeedback(){
  document.getElementById('feedback-correct').classList.add('hidden');
  document.getElementById('feedback-wrong').classList.add('hidden');
}

function choose(side){
  if(locked||paused) return;
  locked=true;
  const q=questions[current];
  if(side===q.answer){
    score+=10; correctCount++;
    document.getElementById('score-val').textContent=score;
    const fb=document.getElementById('feedback-correct');
    fb.classList.remove('hidden'); void fb.offsetWidth; fb.classList.add('feedback-pop');
    playTone(true);
  } else {
    const fb=document.getElementById('feedback-wrong');
    fb.classList.remove('hidden'); void fb.offsetWidth; fb.classList.add('feedback-pop');
    playTone(false);
  }
  if(current%5===4){
    const stageIndex=Math.floor(current/5);
    if(!earnedBadges.includes(stageIndex)) earnedBadges.push(stageIndex);
  }
  setTimeout(()=>{
    current++;
    if(current>=questions.length){ finishGame(); }
    else { renderQuestion(); }
  },1100);
}

function finishGame(){
  clearInterval(timer);
  const isPassed = correctCount >= 20;
  allCleared = isPassed && earnedBadges.length>=5;
  if(allCleared) score+=100;

  document.getElementById('result-score').textContent=score;
  document.getElementById('result-correct').textContent=correctCount;

  const statusEl = document.getElementById('result-reward-status');
  if (isPassed) {
    statusEl.className = "mb-4 p-4 rounded-2xl bg-green-50 text-green-700 font-bold border border-green-200 text-lg";
    statusEl.textContent = "🎉 สุดยอดไปเลย! หนูตอบถูกผ่านเกณฑ์ 20 ข้อ ได้รับสิทธิ์รับเกียรติบัตรสุดพิเศษแล้ว!";
    document.getElementById('btn-view-cert').style.display = '';
  } else {
    statusEl.className = "mb-4 p-4 rounded-2xl bg-amber-50 text-amber-700 font-bold border border-amber-200 text-lg";
    statusEl.textContent = "💪 พยายามอีกนิดนะลูก! ต้องตอบถูกอย่างน้อย 20 ข้อเพื่อรับเกียรติบัตร (ตอนนี้ตอบถูก " + correctCount + " ข้อ) ลองเล่นใหม่อีกครั้งนะครับ!";
    document.getElementById('btn-view-cert').style.display = 'none';
  }

  const list=document.getElementById('badge-list');
  list.innerHTML='';
  earnedBadges.sort((a,b)=>a-b).forEach(i=>{
    const chip=document.createElement('span');
    chip.className='rounded-full px-4 py-2 bg-amber-100 text-amber-800 font-semibold shadow';
    chip.textContent=badges[i];
    list.appendChild(chip);
  });
  if(earnedBadges.length===0){
    const chip=document.createElement('span');
    chip.className='text-slate-500';
    chip.textContent='ยังไม่ได้ Badge ลองเล่นอีกครั้งนะ!';
    list.appendChild(chip);
  }
  showScreen('result');
}

function quitGame(){ clearInterval(timer); stopCamera(); showScreen('home'); }

function togglePause(){
  paused=!paused;
  document.getElementById('btn-pause').style.opacity = paused ? '0.6':'1';
}

/* ================= เสียง (Web Audio API) ================= */
let audioCtx=null;
function playTone(correct){
  try{
    audioCtx = audioCtx || new (window.AudioContext||window.webkitAudioContext)();
    const notes = correct ? [523,659,784] : [330,247];
    let t=audioCtx.currentTime;
    notes.forEach((f)=>{
      const o=audioCtx.createOscillator(), g=audioCtx.createGain();
      o.frequency.value=f; o.type=correct?'triangle':'sawtooth';
      o.connect(g); g.connect(audioCtx.destination);
      g.gain.setValueAtTime(0.001,t); g.gain.exponentialRampToValueAtTime(0.25,t+0.02);
      g.gain.exponentialRampToValueAtTime(0.001,t+0.2);
      o.start(t); o.stop(t+0.22); t+=0.18;
    });
  }catch(e){}
}

/* ================= กล้อง (AR ซ้อนภาพ) ================= */
let stream=null;
async function toggleCamera(){
  if(stream){ stopCamera(); return; }
  document.getElementById('camera-status-home').textContent = 'กำลังตรวจสอบและเชื่อมต่อกล้อง... ⏳';
  
  // ตรวจสอบระบบก่อนเปิดกล้อง
  if (window.location.protocol === 'file:') {
    document.getElementById('camera-status-home').textContent = '⚠️ ห้ามทดสอบโดยเปิดไฟล์แบบ file:// กรุณารันผ่าน localhost หรือ HTTPS เช่น GitHub Pages';
    return;
  }
  
  if (!navigator.mediaDevices || !navigator.mediaDevices.getUserMedia) {
    document.getElementById('camera-status-home').textContent = '❌ ระบบไม่รองรับการเข้าถึงกล้อง (กรุณาเปิดเกมผ่านลิงก์ HTTPS หรือ GitHub Pages และอนุญาตการใช้กล้อง)';
    return;
  }

  const constraints = { video: { facingMode: "environment", width:{ideal:640}, height:{ideal:480} }, audio: false };
  try {
    stream = await navigator.mediaDevices.getUserMedia(constraints);
    const v = document.getElementById('webcam');
    if (v) { v.srcObject = stream; v.classList.remove('hidden'); v.play().catch(()=>{}); }
    const fb = document.getElementById('ar-fallback');
    if (fb) fb.classList.add('hidden');
    document.getElementById('camera-status-home').textContent = 'กล้องเปิดใช้งานแล้ว 📷✨ ยกอุปกรณ์ขึ้นเพื่อดูภาพ AR';
  } catch (e) {
    document.getElementById('camera-status-home').textContent = '⚠️ ไม่สามารถเปิดกล้องได้: กรุณาเปิดเกมผ่านลิงก์ HTTPS หรือ GitHub Pages และอนุญาตการใช้กล้อง เพื่อใช้งานกล้อง AR หรือจะเล่นต่อด้วยปุ่มปกติก็ได้ครับ';
  }
}

function stopCamera(){
  if(stream){ stream.getTracks().forEach(t=>t.stop()); stream=null; }
  const v=document.getElementById('webcam');
  if (v) { v.classList.add('hidden'); v.srcObject=null; }
  const fb = document.getElementById('ar-fallback');
  if (fb) fb.classList.remove('hidden');
  document.getElementById('camera-status-home').textContent='';
}
</script>
 <script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'a186206ea6b8d02a',t:'MTc4MzU4NzUwNC4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>
