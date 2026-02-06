<html lang="ko">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>2026 에코왕곡 교육 프로그램 제안서</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Noto+Sans+KR:wght@300;400;500;700;900&display=swap');
        
        body { font-family: 'Noto Sans KR', sans-serif; background-color: #fdfbf7; color: #44403c; overflow-x: hidden; }
        .card-shadow { box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.05), 0 4px 6px -2px rgba(0, 0, 0, 0.02); }
        .transition-soft { transition: all 0.3s cubic-bezier(0.4, 0, 0.2, 1); }
        .animate-in { animation: fadeIn 0.6s ease-out forwards; }
        @keyframes fadeIn { from { opacity: 0; transform: translateY(20px); } to { opacity: 1; transform: translateY(0); } }
        .bg-invoice { background-color: #fff; background-image: radial-gradient(#e7e5e4 1px, transparent 1px); background-size: 20px 20px; }
        .img-overlay { background: linear-gradient(to top, rgba(0,0,0,0.85) 0%, rgba(0,0,0,0) 70%); }
        .step-badge { position: absolute; top: 20px; left: 20px; background: #ea580c; color: white; padding: 8px 16px; border-radius: 12px; font-weight: 900; z-index: 10; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
        .schedule-tab-active { background-color: #4d7c0f; color: white; box-shadow: 0 4px 6px rgba(0,0,0,0.1); }
        .modal-overlay { background-color: rgba(0, 0, 0, 0.6); backdrop-filter: blur(8px); display: none; position: fixed; inset: 0; z-index: 100; align-items: center; justify-content: center; }
        
        /* 체험명 한 줄 고정 */
        .single-line-title {
            white-space: nowrap;
            overflow: hidden;
            text-overflow: ellipsis;
            font-size: clamp(1.05rem, 2.3vw, 1.35rem);
            line-height: 1.2;
            font-weight: 900;
            display: block;
        }

        /* 하단 배지 깜빡임 애니메이션 */
        .dot-blink-blue { animation: blink-blue 1.5s infinite; background-color: #3b82f6; }
        @keyframes blink-blue { 0%, 100% { opacity: 1; transform: scale(1.1); } 50% { opacity: 0.3; transform: scale(0.8); } }
        .dot-blink-lime { animation: blink-lime 1.5s infinite; background-color: #84cc16; }
        @keyframes blink-lime { 0%, 100% { opacity: 1; transform: scale(1.1); } 50% { opacity: 0.3; transform: scale(0.8); } }
        .dot-blink-orange { animation: blink-orange 1.5s infinite; background-color: #f97316; }
        @keyframes blink-orange { 0%, 100% { opacity: 1; transform: scale(1.1); } 50% { opacity: 0.3; transform: scale(0.8); } }

        .timeline-item::before { content: ''; position: absolute; left: 19px; top: 40px; bottom: -40px; width: 2px; background: #e5e7eb; }
        .timeline-item:last-child::before { display: none; }
    </style>
</head>
<body class="antialiased scroll-smooth text-left">

    <!-- Navigation -->
    <nav class="sticky top-0 z-50 bg-white/95 backdrop-blur-md border-b border-stone-200 shadow-sm h-16 flex items-center">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 w-full flex justify-between items-center">
            <div class="flex items-center gap-2 cursor-pointer" onclick="window.scrollTo({top:0, behavior:'smooth'})">
                <span class="text-2xl font-bold text-lime-700">🌱</span>
                <h1 class="font-black text-xl text-stone-900 tracking-tighter">에코왕곡교육센터</h1>
            </div>
            <div class="hidden md:flex space-x-8">
                <button onclick="scrollToId('strengths')" class="text-stone-600 hover:text-lime-700 font-bold text-sm transition-soft">기관강점</button>
                <button onclick="scrollToId('annual')" class="text-stone-600 hover:text-lime-700 font-bold text-sm transition-soft">연간계획</button>
                <button onclick="scrollToId('wood-project')" class="text-orange-600 hover:text-orange-700 font-black text-sm transition-soft">시그니처목공</button>
                <button onclick="scrollToId('schedule')" class="text-stone-600 hover:text-lime-700 font-bold text-sm transition-soft">일정표</button>
                <button onclick="showModal()" class="bg-lime-900 text-white px-6 py-2 rounded-full font-black text-sm hover:bg-black shadow-md">상담 신청</button>
            </div>
        </div>
    </nav>

    <!-- Hero Section -->
    <section class="relative h-[85vh] flex items-center justify-center overflow-hidden bg-stone-900 text-center text-white text-balance">
        <div class="absolute inset-0">
            <img src="hero.jpg" alt="에코왕곡 메인" class="w-full h-full object-cover opacity-60" onerror="this.onerror=null; this.src='https://images.unsplash.com/photo-1596461404969-9ae70f2830c1?auto=format&fit=crop&w=1600&q=80';" />
        </div>
        <div class="relative z-10 max-w-5xl mx-auto px-4 animate-in text-center">
            <div class="inline-flex items-center px-4 py-2 rounded-full bg-lime-500/20 border border-lime-400 text-lime-300 font-bold text-xs mb-8 tracking-widest uppercase shadow-lg tracking-tighter">🏆 전국 으뜸촌 & 2025 스타마을 선정 기관</div>
            <h1 class="text-5xl md:text-8xl font-black mb-8 leading-tight tracking-tighter italic">자연이 아이들의 <br/> <span class="text-lime-400 font-black tracking-normal font-black">선생님</span>이 됩니다</h1>
            <p class="text-xl md:text-2xl text-stone-100 mb-12 font-medium leading-relaxed drop-shadow-md">누리과정 연계 프리미엄 생태·환경교육 <br/><span class="font-black text-lime-400 underline decoration-wavy underline-offset-8">10년 이상의 독보적 노하우</span>로 완성된 명품 수업</p>
            <div class="flex flex-wrap justify-center gap-6">
                <button onclick="scrollToId('annual')" class="px-10 py-4 bg-lime-600 text-white font-black rounded-2xl shadow-xl hover:bg-lime-700 transition-soft transform hover:-translate-y-1">2026 연간 계획 보기</button>
                <button onclick="showModal()" class="px-10 py-4 bg-white/10 backdrop-blur-md border border-white/30 text-white font-black rounded-2xl hover:bg-white/20 transition-soft">상담 및 예약 신청</button>
            </div>
        </div>
    </section>

    <main class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 py-20 space-y-32">

        <!-- 1. 기관 강점 -->
        <section id="strengths" class="animate-in text-center text-center">
            <div class="mb-20 text-balance text-center">
                <h2 class="text-base text-lime-600 font-black tracking-widest uppercase mb-4 text-center">History & Quality</h2>
                <p class="text-4xl font-black text-stone-900 leading-tight tracking-tighter text-center">에코왕곡교육센터 10년의 신뢰</p>
                <p class="mt-6 text-stone-500 max-w-2xl mx-auto font-medium text-center">대한민국 농촌 교육의 표준을 제시합니다. 10년간 수많은 교육 기관의 선택을 받아온 전문성을 약속합니다.</p>
            </div>
            <div class="grid md:grid-cols-3 gap-8">
                <div class="p-10 rounded-[48px] bg-white border border-stone-100 card-shadow transition-soft hover:-translate-y-2 text-center text-center">
                    <div class="text-5xl mb-6 text-center">🏅</div>
                    <h3 class="font-black text-xl text-stone-900 mb-4 tracking-tight font-black text-lime-800 text-center">국가인증 1등급 기관</h3>
                    <p class="text-stone-500 text-sm leading-relaxed font-bold text-center">농식품부 '으뜸촌' 및 교육부 인증기관. 국가가 보증하는 안전과 품질을 약속합니다.</p>
                </div>
                <div class="p-10 rounded-[48px] bg-white border border-stone-100 card-shadow transition-soft hover:-translate-y-2 text-center text-center">
                    <div class="text-5xl mb-6 text-center">📚</div>
                    <h3 class="font-black text-xl text-stone-900 mb-4 tracking-tight font-black text-lime-800 text-center">누리과정 밀착 설계</h3>
                    <p class="text-stone-500 text-sm leading-relaxed font-bold text-center">월별 생활주제와 아이들의 발달 단계에 최적화된 [체험+놀이+이야기] 커리큘럼을 제공합니다.</p>
                </div>
                <div class="p-10 rounded-[48px] bg-white border border-stone-100 card-shadow transition-soft hover:-translate-y-2 text-center text-center">
                    <div class="text-5xl mb-6 text-center">👨‍🏫</div>
                    <h3 class="font-black text-xl text-stone-900 mb-4 tracking-tight font-black text-lime-800 text-center">전문 강사 직접 지도</h3>
                    <p class="text-stone-500 text-sm leading-relaxed font-bold text-center text-center">자격증을 보유한 목공 전문 강사진이 교실로 찾아갑니다. 아이들의 안전과 성장을 책임집니다.</p>
                </div>
            </div>
        </section>

        <!-- 2. 연간 계획 -->
        <section id="annual">
            <div class="mb-20 text-left text-left">
                <h2 class="text-base text-lime-600 font-black tracking-widest uppercase mb-4 text-left">Educational Roadmap</h2>
                <p class="text-4xl font-black text-stone-900 italic font-serif leading-tight tracking-tighter text-left">2026학년도 연간 교육 계획</p>
                <div class="flex flex-wrap gap-2 mt-10 p-1 bg-stone-100 rounded-2xl border border-stone-200 inline-flex shadow-inner font-bold text-left text-xs md:text-sm">
                    <button onclick="updateFilter('all')" id="f-all" class="px-5 py-2 rounded-xl text-xs font-black transition-soft bg-white shadow-sm text-lime-800">전체</button>
                    <button onclick="updateFilter('spring')" id="f-spring" class="px-5 py-2 rounded-xl transition-soft text-stone-500 hover:bg-white/50 font-bold">봄</button>
                    <button onclick="updateFilter('summer')" id="f-summer" class="px-5 py-2 rounded-xl transition-soft text-stone-500 hover:bg-white/50 font-bold">여름</button>
                    <button onclick="updateFilter('autumn')" id="f-autumn" class="px-5 py-2 rounded-xl transition-soft text-stone-500 hover:bg-white/50 font-bold">가을</button>
                    <button onclick="updateFilter('winter')" id="f-winter" class="px-5 py-2 rounded-xl transition-soft text-stone-500 hover:bg-white/50 font-bold">겨울</button>
                </div>
                <p class="mt-6 text-stone-400 text-xs font-bold flex items-center gap-1 italic"><span class="text-orange-600 font-black mr-1">※</span> 본 이미지는 예시이며, 실제 활동 및 완성품은 교육 여건에 따라 변경될 수 있습니다.</p>
            </div>
            <div id="curriculum-grid" class="grid grid-cols-1 md:grid-cols-2 gap-10 text-left"></div>
        </section>

        <!-- 3. 시그니처 목공 -->
        <section id="wood-project" class="bg-stone-900 rounded-[80px] p-12 md:p-24 overflow-hidden relative">
            <div class="absolute right-0 top-0 w-1/3 h-full bg-orange-600/5 pointer-events-none"></div>
            <div class="relative z-10 text-center text-white">
                <span class="text-orange-400 font-black tracking-widest uppercase text-xs mb-4 block text-center">Premium Woodcraft Project</span>
                <h2 class="text-4xl md:text-5xl font-black text-white mb-6 tracking-tighter italic font-serif text-center text-center">"나무와 친해지기 3.0"</h2>
                <p class="text-lg text-stone-400 max-w-3xl mx-auto font-medium leading-relaxed italic mb-10 text-center text-balance text-center">"10년 이상 현장에서 검증된 국내 유일의 3차시 연속성 목공 프로젝트입니다."</p>
                <p class="mb-20 text-stone-500 text-[11px] font-bold text-center text-center">※ 목공 완성품은 연령 및 원의 상황에 따라 디자인이 세련되게 변경될 수 있습니다.</p>

                <div class="grid lg:grid-cols-3 gap-10 text-left">
                    <div class="bg-white/5 backdrop-blur-md rounded-[56px] overflow-hidden border border-white/10 hover:border-orange-500/50 transition-soft flex flex-col h-full shadow-lg group text-left">
                        <div class="h-64 relative text-left">
                            <span class="step-badge">1차</span>
                            <img src="wood1.jpg" class="w-full h-full object-cover transition-soft group-hover:scale-110" onerror="this.onerror=null; this.src='https://images.unsplash.com/photo-1510915361894-db8b60106cb1?auto=format&fit=crop&w=800&q=80';" />
                            <div class="absolute inset-0 img-overlay flex items-end p-8 text-left text-left"><h3 class="text-white text-2xl font-black text-left">도구의 발견</h3></div>
                        </div>
                        <div class="p-10 flex-grow text-left">
                            <h4 class="text-[11px] font-black text-orange-400 uppercase tracking-widest mb-3 text-left">Discovery</h4>
                            <p class="text-sm text-stone-400 leading-relaxed font-medium text-left">나무와 나무못을 자유롭게 두드리며 성질을 익히고 정서적 해소감을 얻는 기초 단계입니다.</p>
                            <p class="text-xs text-lime-400 mt-2 font-bold italic text-left">* 동물 못박기 세트 1인 1개 제공</p>
                        </div>
                    </div>
                    <div class="bg-white/5 backdrop-blur-md rounded-[56px] overflow-hidden border border-white/10 hover:border-orange-500/50 transition-soft flex flex-col h-full shadow-lg group border-2 border-lime-500/30 text-left text-left">
                        <div class="h-64 relative text-left text-left">
                            <span class="step-badge">2차</span>
                            <img src="wood2.jpg" class="w-full h-full object-cover transition-soft group-hover:scale-110" onerror="this.onerror=null; this.src='https://images.unsplash.com/photo-1545558014-8692077e9b5c?auto=format&fit=crop&w=800&q=80';" />
                            <div class="absolute inset-0 img-overlay flex items-end p-8 text-left text-left text-left text-left"><h3 class="text-white text-2xl font-black text-left text-left text-left">기술의 완성</h3></div>
                        </div>
                        <div class="p-10 flex-grow text-left text-left text-left">
                            <h4 class="text-[11px] font-black text-orange-400 uppercase tracking-widest mb-3 text-left">Structure</h4>
                            <div class="flex flex-wrap gap-2 mb-4 text-left">
                                <span class="bg-lime-600/20 text-lime-400 text-[10px] px-2 py-0.5 rounded border border-lime-500/30 font-black">자동차</span>
                                <span class="bg-lime-600/20 text-lime-400 text-[10px] px-2 py-0.5 rounded border border-lime-500/30 font-black">새싹화분</span>
                                <span class="bg-lime-600/20 text-lime-400 text-[10px] px-2 py-0.5 rounded border border-lime-500/30 font-black">캐릭터연필꽂이</span>
                            </div>
                            <p class="text-sm text-stone-400 leading-relaxed font-medium text-left">1차 지식을 바탕으로 드라이버와 망치를 활용해 실제 기능을 가진 작품을 완성합니다.</p>
                        </div>
                    </div>
                    <div class="bg-white/5 backdrop-blur-md rounded-[56px] overflow-hidden border border-white/10 hover:border-orange-500/50 transition-soft flex flex-col h-full shadow-lg group text-left text-left text-left">
                        <div class="h-64 relative text-left text-left text-left text-left">
                            <span class="step-badge bg-lime-600">3차</span>
                            <img src="wood3.jpg" class="w-full h-full object-cover transition-soft group-hover:scale-110" onerror="this.onerror=null; this.src='https://images.unsplash.com/photo-1601628122822-4876b539401b?auto=format&fit=crop&w=800&q=80';" />
                            <div class="absolute inset-0 img-overlay flex items-end p-8 text-left text-left text-left text-left text-left"><h3 class="text-white text-2xl font-black text-left text-left text-left text-left">이야기의 확장</h3></div>
                        </div>
                        <div class="p-10 flex-grow text-left text-left text-left text-left">
                            <h4 class="text-[11px] font-black text-orange-400 uppercase tracking-widest mb-3 text-left">Storytelling</h4>
                            <p class="text-sm text-stone-400 leading-relaxed font-medium text-left">나만의 마을을 구성하고 목공 인형을 통해 따뜻한 이야기를 완성하는 하이라이트 단계입니다.</p>
                        </div>
                    </div>
                </div>

                <div class="mt-20 bg-gradient-to-r from-orange-600 to-orange-700 rounded-[64px] p-12 flex flex-col md:flex-row items-center justify-between gap-12 text-left shadow-2xl border border-orange-500/20 text-left">
                    <div class="max-w-xl text-left">
                        <h4 class="text-3xl font-black text-white mb-6 font-serif italic text-left">준비물 걱정 없는 '출장 안심' 시스템</h4>
                        <ul class="grid sm:grid-cols-2 gap-4 text-orange-50 font-bold text-sm text-left">
                            <li class="flex items-center gap-2">✅ 재료 세팅부터 뒷정리까지 완벽 책임</li>
                            <li class="flex items-center gap-2 text-left">✅ 전문 목공 강사 직접 지도 (자격 보유)</li>
                            <li class="flex items-center gap-2 text-left text-left">✅ 연령별 발달 단계 맞춤형 교구 제공</li>
                            <li class="flex items-center gap-2 text-left text-left">✅ 저소음 작업 패드 사용 (층간소음 방지)</li>
                        </ul>
                    </div>
                    <button onclick="showModal()" class="bg-white text-orange-600 px-14 py-7 rounded-3xl font-black text-xl shadow-2xl hover:bg-orange-50 transition transform hover:scale-105 active:scale-95 text-center font-black uppercase">상담 신청하기</button>
                </div>
            </div>
        </section>

        <!-- 4. 특별 행사 및 일정표 -->
        <section id="schedule" class="animate-in text-center text-center text-center">
            <div class="mb-20">
                <h2 class="text-base text-orange-600 font-black tracking-widest uppercase mb-4 text-center">Seasonal Special</h2>
                <p class="text-4xl font-black text-stone-900 leading-tight tracking-tighter text-center text-center text-center">함께 웃고 추억하는 특별 행사</p>
                <p class="mt-6 text-stone-500 max-w-2xl mx-auto font-medium text-center">에코왕곡의 특별 행사는 단순한 대관이 아닙니다. 대표님의 직접 진행과 10년의 노하우가 결합된 '올인원 패키지'입니다.</p>
            </div>
            
            <div class="grid md:grid-cols-2 gap-8 mb-24 text-left text-left">
                <div class="bg-white rounded-[48px] overflow-hidden border border-stone-200 shadow-sm flex flex-col transition-soft hover:shadow-2xl text-left">
                    <div class="h-64 relative bg-lime-900 overflow-hidden text-center text-center">
                        <img src="sports.jpg.png" class="w-full h-full object-cover opacity-60 text-center" onerror="this.onerror=null; this.src='https://images.unsplash.com/photo-1530143311094-34d807799e8f?auto=format&fit=crop&w=600&q=80';" />
                        <div class="absolute inset-0 flex items-center justify-center text-center text-center text-center"><h3 class="text-white text-3xl font-black drop-shadow-md text-center text-center text-center">🚩 명랑 운동회</h3></div>
                    </div>
                    <div class="p-10 space-y-6 text-left">
                        <ul class="space-y-4 text-stone-600 font-bold text-left text-left">
                            <li class="flex gap-3 text-left">✅ <span class="text-lime-700 font-black text-left">대표님 직접 진행 (MC비 무료 혜택)</span></li>
                            <li class="flex gap-3 text-left text-left">✅ 대형 천연 잔디 마당 원 단독 사용</li>
                            <li class="flex gap-3 text-left text-left text-left text-left">✅ 음향 장비 및 행사 물품 일체 지원</li>
                        </ul>
                        <button onclick="switchSchedule('sports'); scrollToId('sched-view');" class="w-full py-4 bg-lime-600 text-white font-black rounded-2xl transition hover:bg-lime-700 text-center font-black uppercase shadow-lg text-center text-center">운동회 일정표 보기</button>
                    </div>
                </div>
                <div class="bg-white rounded-[48px] overflow-hidden border border-stone-200 shadow-sm flex flex-col transition-soft hover:shadow-2xl text-left text-left">
                    <div class="h-64 relative bg-stone-800 overflow-hidden text-center text-center text-center text-center text-center">
                        <img src="camp.jpg.png" class="w-full h-full object-cover opacity-60 text-center text-center" onerror="this.onerror=null; this.src='https://images.unsplash.com/photo-1478131143081-80f7f84ca84d?auto=format&fit=crop&w=600&q=80';" />
                        <div class="absolute inset-0 flex items-center justify-center text-center text-center text-center text-center text-center text-center text-center"><h3 class="text-white text-3xl font-black drop-shadow-md text-center text-center text-center text-center text-center">⛺ 졸업 여행</h3></div>
                    </div>
                    <div class="p-10 space-y-6 text-left text-left">
                        <ul class="space-y-4 text-stone-600 font-bold text-left text-left">
                            <li class="flex gap-3 text-left text-left">✅ 1박 2일 따뜻한 온돌 숙박 보장</li>
                            <li class="flex gap-3 text-left text-left">✅ <span class="text-orange-600 font-black text-left">LED 불멍 & 촛불의식 무료 진행</span></li>
                            <li class="flex gap-3 text-left text-left text-left text-left">✅ 저녁(BBQ)+아침+점심 3식 풀패키지</li>
                        </ul>
                        <button onclick="switchSchedule('grad'); scrollToId('sched-view');" class="w-full py-4 bg-orange-600 text-white font-black rounded-2xl transition hover:bg-orange-700 text-center font-black uppercase shadow-lg text-center text-center">졸업여행 일정표 보기</button>
                    </div>
                </div>
            </div>

            <!-- 타임라인 일정표 -->
            <div id="sched-view" class="pt-20 text-center text-center">
                <div class="flex justify-center gap-3 mb-16 overflow-x-auto pb-4 text-center">
                    <button onclick="switchSchedule('basic')" id="s-btn-basic" class="schedule-tab-active px-8 py-3 rounded-full text-sm font-black transition-soft text-center font-black">일반 체험</button>
                    <button onclick="switchSchedule('sports')" id="s-btn-sports" class="bg-stone-100 text-stone-500 px-8 py-3 rounded-full text-sm font-black hover:bg-stone-200 transition-soft font-bold text-center">명랑 운동회</button>
                    <button onclick="switchSchedule('grad')" id="s-btn-grad" class="bg-stone-100 text-stone-500 px-8 py-3 rounded-full text-sm font-black hover:bg-stone-200 transition-soft font-bold text-center">졸업 여행</button>
                </div>
                <div class="max-w-2xl mx-auto text-left relative pl-12 mb-32 text-left">
                    <div id="schedule-content" class="space-y-12 text-left text-left"></div>
                </div>
            </div>
        </section>

        <!-- 5. 견적 계산기 (오각형 삭제 및 중앙 배치) -->
        <section id="calculator" class="pt-32 border-t border-stone-200 text-center text-center text-center">
            <div class="max-w-3xl mx-auto text-center">
                <div class="mb-16">
                    <span class="inline-block bg-lime-100 text-lime-700 px-4 py-1 rounded-full text-xs font-black uppercase mb-4 tracking-widest font-black">Nuri-Curriculum Alignment 98%</span>
                    <h2 class="text-4xl font-black text-stone-900 leading-tight tracking-tighter text-center">스마트 맞춤 견적 산출</h2>
                    <p class="mt-6 text-stone-500 font-medium text-center">누리과정 5대 영역을 골고루 담은 에코왕곡의 교육 가치입니다.</p>
                </div>

                <div class="bg-white bg-invoice p-12 md:p-16 rounded-[64px] border border-stone-300 card-shadow flex flex-col text-left text-left">
                    <div class="flex justify-between items-center mb-12 pb-8 border-b-2 border-dashed border-stone-300 text-left text-left">
                        <div class="text-left text-left"><span class="bg-stone-800 text-white text-[10px] px-2 py-1 rounded font-black tracking-widest uppercase text-left">Estimator</span><h2 class="text-3xl font-black mt-3 text-stone-800 tracking-tighter text-left">견적 미리보기</h2></div>
                        <div class="text-right text-right"><div id="total-price" class="text-5xl font-black text-lime-700 tracking-tighter italic text-right font-black">0원</div><p class="text-stone-400 text-[10px] uppercase mt-1 tracking-widest text-right font-black font-black">VAT Not Included</p></div>
                    </div>
                    <div class="space-y-10 text-left text-left">
                        <div class="text-left text-left text-left text-left">
                            <label class="block text-[11px] font-black text-stone-400 mb-4 tracking-widest uppercase text-left">Attendance Count</label>
                            <input type="number" id="in-child" value="25" class="w-full px-8 py-5 rounded-[32px] border-2 border-stone-50 bg-stone-50 focus:bg-white focus:border-lime-500 outline-none text-4xl font-black transition-soft text-left font-black" />
                        </div>
                        <div class="flex items-center justify-between p-8 bg-stone-50 rounded-[40px] border border-stone-100 text-left text-left text-left">
                            <div class="text-left text-left text-left">
                                <span class="block text-lg font-black text-stone-800 tracking-tight text-left font-black text-left">나주 로컬 점심 식단</span>
                                <span class="text-[13px] text-stone-400 font-bold italic block mt-1 leading-none text-left font-black">친환경 건강 식단 (1인 8,000원 추가)</span>
                            </div>
                            <input type="checkbox" id="in-meal" class="w-12 h-12 text-lime-600 rounded-3xl focus:ring-lime-500 cursor-pointer accent-lime-600 shadow-sm text-left" />
                        </div>
                        <button onclick="showModal()" class="w-full py-7 bg-stone-900 text-white font-black rounded-[40px] hover:bg-black transition transform hover:scale-105 shadow-2xl text-2xl tracking-tight uppercase text-center font-black font-black">상담 신청 및 예약하기</button>
                    </div>
                </div>
            </div>
        </section>
    </main>

    <!-- Footer -->
    <footer class="bg-stone-900 text-stone-500 py-24 border-t border-white/5 text-center font-bold text-center text-center">
        <div class="max-w-7xl mx-auto px-4 text-center">
            <h2 class="text-4xl font-black text-white mb-10 tracking-tighter uppercase tracking-[0.2em] text-center">에코왕곡교육센터</h2>
            <div class="flex flex-col md:flex-row justify-center gap-12 text-sm mb-20 tracking-[0.1em] text-center text-center text-center">
                <span class="flex items-center gap-3 text-center text-center text-center"><span class="w-2.5 h-2.5 bg-lime-500 rounded-full dot-blink-lime text-center font-black"></span> 전국 으뜸촌 지정</span>
                <span class="flex items-center gap-3 text-center text-center text-center text-center"><span class="w-2.5 h-2.5 bg-orange-500 rounded-full dot-blink-orange text-center font-black"></span> 전남 2025 스타마을</span>
                <span class="flex items-center gap-3 text-center text-center text-center text-center text-center text-center text-center text-center"><span class="w-2.5 h-2.5 bg-blue-500 rounded-full dot-blink-blue text-center font-black"></span> 교육부 인증기관</span>
            </div>
            <p class="text-sm opacity-70 mb-4 text-center font-black">전라남도 나주시 왕곡면 나주서부로 371-14 | 061-335-8101</p>
            <p class="text-lg font-black text-stone-200 italic text-center font-black">📞 사무장 박선율 010-8680-8101</p>
            <p class="text-[10px] mt-16 tracking-widest text-stone-700 uppercase font-black text-center text-center text-center">Copyright © 2026 Eco Wanggok. All rights reserved.</p>
        </div>
    </footer>

    <!-- 상담 신청 모달 -->
    <div id="reservation-modal" class="modal-overlay" onclick="closeModal()">
        <div class="bg-white rounded-[48px] max-w-lg w-full p-10 card-shadow border border-stone-200 animate-in text-center shadow-2xl" onclick="event.stopPropagation()">
            <div class="text-5xl mb-6 text-center text-center text-center">📬</div>
            <h2 class="text-3xl font-black text-lime-800 mb-2 font-black tracking-tight text-center">상담 및 예약 신청</h2>
            <p class="text-stone-500 font-bold mb-10 text-center font-bold">10년의 신뢰로 정성껏 안내해 드립니다.</p>
            <div class="space-y-4 mb-12 text-left">
                <div class="bg-stone-50 p-6 rounded-3xl border flex items-center gap-4 text-left"><span class="text-2xl text-center">👤</span><div><p class="text-xs text-stone-400 font-black uppercase tracking-widest font-black text-left">상담 담당자</p><p class="text-xl font-black text-stone-800 font-black tracking-tight text-left">박선율 사무장</p></div></div>
                <div class="bg-lime-50 p-6 rounded-3xl border flex items-center gap-4 text-left text-left text-left"><span class="text-2xl text-center text-center">📞</span><div><p class="text-xs text-lime-600 font-black uppercase tracking-widest font-black text-left">직통 번호</p><p class="text-xl font-black text-lime-900 font-black tracking-tight text-left text-left">010-8680-8101</p></div></div>
            </div>
            <div class="flex flex-col gap-3">
                <button onclick="window.location.href='tel:01086808101'" class="w-full py-5 bg-lime-600 text-white rounded-2xl font-black text-lg shadow-lg hover:bg-lime-700 transition font-black">사무장님께 전화 걸기</button>
                <button onclick="window.location.href='sms:01086808101?body=[에코왕곡] 제안서 보고 연락드렸습니다. 원명 및 인원:'" class="w-full py-5 bg-stone-800 text-white rounded-2xl font-black text-lg shadow-lg hover:bg-stone-900 transition font-black">문의 문자 남기기</button>
                <button onclick="closeModal()" class="w-full py-4 text-stone-400 font-bold text-center font-black">창 닫기</button>
            </div>
        </div>
    </div>

    <script>
        const curriculum = [
            { m: 3, season: 'spring', theme: '우리 원과 친구', title: '🌱커피박 반려식물심기', img: 'photo3.jpg', p: '흙과 커피 가루의 촉감 놀이', e: '커피박 화분 자원순환 탐구', c: '단짝 식물 친구 직접 고르기', comp: '나만의 그림 화분 완성' },
            { m: 4, season: 'spring', theme: '봄꽃과 향기', title: '🌸봄을담은 감성디퓨저', img: 'photo4.jpg', p: '마당 꽃 향기 따라 숨바꼭질', e: '보존화의 색감과 결 관찰', c: '나만의 꽃 레이어드 선택', comp: '선물용 봄 디퓨저 완성' },
            { m: 5, season: 'spring', theme: '나와 가족', title: '🌷감사가득 카네이션바구니', img: 'photo5.jpg', p: '대형 비눗방울과 신체 놀이', e: '카네이션 비누꽃 질감 탐색', c: '리본 및 꽃 색상 주도적 선택', comp: '감사 가득 바구니 완성' },
            { m: 6, season: 'summer', theme: '도구와 목공', title: '🔨뚝딱뚝딱 원목건축놀이', img: 'photo6.jpg', p: '원목 자투리 쌓고 무너뜨리기', e: '나무의 결 사포질로 느껴보기', c: '최적의 나무 조각 직접 선택', comp: '꼬마 목수 수료 작품 완성' },
            { m: 7, season: 'summer', theme: '여름과 물놀이', title: '🧅나주양파 천연손수건염색', img: 'photo7.jpg', p: '바스락 양파 껍질 소리 놀이', e: '염색 물의 신비로운 변화 관찰', c: '고무줄 무늬 위치 스스로 결정', comp: '황금빛 천연 손수건 완성' },
            { m: 8, season: 'summer', theme: '건강과 여름', title: '🍧오감만족 과일컵빙수요리', img: 'photo8.jpg', p: '꽁꽁 얼음 속 보물 구출 작전', e: '얼음 입자와 과일 향 탐색', c: '나만의 토핑 레시피 구성', comp: '달콤 시원한 컵빙수 맛보기' },
            { m: 9, season: 'autumn', theme: '전통과 추석', title: '🍡알록달록 캐릭터떡빚기', img: 'photo9.jpg', p: '대형 윷놀이와 투호 던지기', e: '천연 반죽의 말랑한 촉감 탐구', c: '만들고 싶은 캐릭터 직접 선택', comp: '정성을 담은 캐릭터 떡 완성' },
            { m: 10, season: 'autumn', theme: '가을 열매와 감성', title: '💡가을압화 LED무드등', img: 'photo10.jpg', p: '바스락 낙엽 숲 산책과 탐험', e: '빛을 투과하는 자연물 관찰', c: '나만의 가을 조각들 배치', comp: '가을밤 감성 무드등 완성' },
            { m: 11, season: 'autumn', theme: '우리 쌀과 농업', title: '🥢가래떡 초코퐁듀빼빼로', img: 'photo11.jpg', p: '가래떡 징검다리 건너기 놀이', e: '초콜릿의 온도별 성질 탐색', c: '알록달록 토핑 가루 직접 선택', comp: '건강한 우리 쌀 디저트 완성' },
            { m: 12, season: 'winter', theme: '추억과 파티', title: '🎂메리에코 루돌프케이크', img: 'photo12.jpg', p: '솔방울 볼링 게임으로 대결', e: '부드러운 크림의 질감 탐색', c: '루돌프의 표정 주도적 결정', comp: '특별한 크리스마스 케이크' },
            { m: 1, season: 'winter', theme: '새해와 전통', title: '🧧자개스티커 꽃거울꾸미기', img: 'photo1.jpg', p: '전통 팽이와 제기차기 시합', e: '오로라 빛 자개의 아름다움 관찰', c: '꽃잎 자개의 배치와 색상 결정', comp: '전통 자개 꽃 손거울 완성' },
            { m: 2, season: 'winter', theme: '나의 성장', title: '🪵 안녕,나를닮은 나무인형', img: 'photo2.jpg', p: '나만의 단짝 나뭇가지 찾기', e: '나뭇가지에 나의 모습 투영하기', c: '인형의 머리카락과 옷감 선택', comp: '나를 닮은 나무친구 완성' }
        ];

        const schedData = {
            basic: [{t:"10:30",a:"도착 및 오리엔테이션",d:"반가워요 에코왕곡! 안전 약속 및 화장실 이용"},{t:"10:50",a:"경험 1차: 놀이와 탐색",d:"주제별 자연물과 교감하며 호기심 깨우기"},{t:"11:40",a:"경험 2차: 선택과 완성",d:"나만의 주도적 작품 완성 및 성취감 느끼기"},{t:"12:30",a:"점심 식사 (건강 식단)",d:"나주 친환경 식재료로 만든 맛있는 점심"},{t:"14:00",a:"마당 비눗방울 및 귀가",d:"추억을 가득 담아 안전하게 배웅"}],
            sports: [{t:"10:30",a:"개회식 및 몸풀기 율동",d:"대표님 직접 진행: 온 가족이 하나 되는 시작"},{t:"11:00",a:"명랑 운동회 메인 게임",d:"지구를 굴려라, 색판 뒤집기 등 협동 활동"},{t:"12:00",a:"가족 점심 식사 & 휴식",d:"잔디밭 위에서 즐기는 맛있는 소풍 시간"},{t:"13:00",a:"보물찾기 & 포토타임",d:"마을 곳곳 보물 찾기와 가족 인생샷 남기기"},{t:"14:30",a:"폐회식 및 귀가",d:"기념 선물 증정 및 안전한 배웅"}],
            grad: [{t:"16:00",a:"도착 및 숙소 배정",d:"따뜻한 온돌 숙소 배정 및 안전 교육"},{t:"18:30",a:"저녁 식사 (BBQ/수육)",d:"친구들과 함께 먹는 꿀맛 같은 저녁 파티"},{t:"19:30",a:"LED 불멍 & 촛불 의식",d:"대표님 진행: 고마운 마음을 전하는 감동의 밤"},{t:"21:00",a:"취침 준비",d:"꿈나라로 여행 떠나기"},{t:"08:30",a:"조식 및 귀가 준비",d:"든든한 아침 먹고 추억 가득 담아 귀가"}]
        };

        function scrollToId(id) { const el = document.getElementById(id); if(el) el.scrollIntoView({ behavior: 'smooth' }); }
        function showModal() { document.getElementById('reservation-modal').style.display = 'flex'; }
        function closeModal() { document.getElementById('reservation-modal').style.display = 'none'; }
        
        function switchSchedule(type) {
            const container = document.getElementById('schedule-content'); container.innerHTML = '';
            ['basic','sports','grad'].forEach(t => { const btn = document.getElementById(`s-btn-${t}`); if(btn) btn.className = (t === type) ? "schedule-tab-active px-8 py-3 rounded-full text-sm font-black transition-soft shadow-md font-black text-center" : "bg-stone-100 text-stone-500 px-8 py-3 rounded-full text-sm font-black hover:bg-stone-200 transition-soft font-bold text-center"; });
            schedData[type].forEach(s => { container.innerHTML += `
                <div class="relative pl-10 timeline-item group text-left">
                    <div class="absolute left-0 top-1 w-10 h-10 rounded-full bg-white border-2 border-stone-200 flex items-center justify-center z-10 group-hover:border-lime-500 transition-colors duration-300 text-left">
                        <span class="w-2.5 h-2.5 rounded-full bg-stone-200 group-hover:bg-lime-600"></span>
                    </div>
                    <div class="text-left text-left">
                        <div class="inline-block px-3 py-1 rounded-lg bg-lime-50 text-lime-700 text-[10px] font-black uppercase mb-2 font-black text-left">${s.t}</div>
                        <h4 class="font-black text-stone-800 text-lg mb-1 group-hover:text-lime-700 transition-colors font-black text-left">${s.a}</h4>
                        <p class="text-sm text-stone-500 font-bold leading-relaxed font-bold text-left">${s.d}</p>
                    </div>
                </div>`; });
        }

        function updateFilter(season) {
            const grid = document.getElementById('curriculum-grid'); grid.innerHTML = '';
            ['all', 'spring', 'summer', 'autumn', 'winter'].forEach(s => { const btn = document.getElementById(`f-${s}`); if(btn) btn.className = (s === season) ? "px-5 py-2 rounded-xl text-xs font-black transition-soft bg-white shadow-sm text-lime-800 font-black font-black" : "px-5 py-2 rounded-xl text-xs transition-soft text-stone-500 hover:bg-white/50 font-bold font-bold"; });
            const filtered = season === 'all' ? curriculum : curriculum.filter(d => d.season === season);
            filtered.forEach(item => { grid.innerHTML += `<div class="bg-white rounded-[56px] overflow-hidden shadow-sm border border-stone-200 flex flex-col md:flex-row transition-soft hover:shadow-2xl group animate-in h-full"><div class="md:w-2/5 h-64 md:h-auto relative overflow-hidden bg-stone-100"><img src="${item.img}" class="w-full h-full object-cover transition-soft group-hover:scale-110 duration-1000" onerror="this.onerror=null; this.src='https://images.unsplash.com/photo-1540324155974-7523202daa3f?auto=format&fit=crop&w=600&q=80';" /><div class="absolute top-6 left-6 bg-white/90 backdrop-blur px-4 py-2 rounded-2xl text-[12px] font-black text-stone-800 shadow-sm text-center font-black font-black font-black">${item.m}월</div></div><div class="p-10 md:w-3/5 text-left text-left text-left"><p class="text-[11px] font-black text-orange-600 uppercase tracking-widest mb-2 text-left font-black font-black font-black">${item.theme}</p><h3 class="font-black text-stone-900 mb-6 tracking-tight text-left single-line-title text-center font-black font-black font-black text-left font-black font-black font-black">${item.title}</h3><div class="space-y-4 text-left text-left text-left"><p class="text-xs text-stone-500 font-bold text-left font-bold font-bold font-black"><span class="text-lime-700 font-black mr-2 text-left font-black font-black font-black font-black">Play.</span> ${item.p}</p><p class="text-xs text-stone-500 font-bold text-left font-bold font-bold font-bold font-black text-left font-black font-black"><span class="text-orange-600 font-black mr-2 text-left font-black font-black font-black font-black">Explore.</span> ${item.e}</p><p class="text-xs text-stone-500 font-bold text-left font-bold font-bold font-bold font-black text-left font-black font-black"><span class="text-blue-600 font-black mr-2 text-left font-black font-black font-black font-black">Choose.</span> ${item.c}</p><p class="text-xs text-stone-800 font-black text-left font-black italic text-left font-black font-black text-left font-black font-black font-black font-black"><span class="mr-2 text-left font-black font-black font-black text-lime-700 text-left">✨</span> ${item.comp}</p></div></div></div>`; });
        }

        function calculate() { const childCnt = parseInt(document.getElementById('in-child').value) || 0; const hasMeal = document.getElementById('in-meal').checked; const total = (childCnt * 15000) + (hasMeal ? childCnt * 8000 : 0); document.getElementById('total-price').textContent = total.toLocaleString() + '원'; }
        
        window.onload = () => { 
            updateFilter('all'); switchSchedule('basic'); calculate(); 
            document.getElementById('in-child').addEventListener('input', calculate); 
            document.getElementById('in-meal').addEventListener('change', calculate); 
        };
    </script>
</body>
</html>
