# 模块四：实战对练界面（AI Practice Interface）

> 来源: 飞书文档「前端代码-松鼠ai培训助手前端界面」
> 模块: 实战对练界面 · Module 4/9

---

文件：ai-practice.html · 亮色主题（parent-anxious 橙色调）
① Tailwind Config 色板配置
代码块
<script id="tailwind-config">
        tailwind.config = {
          darkMode: "class",
          theme: {
            extend: {
              "colors": {
                      "on-tertiary-fixed-variant": "#005236",
327
328
329
330
331
332
333
334
335
336
337
338
339
340
341
342
343
344
345
346
347
348
349
350
351
1
2
3
4
5
6
7


                      "surface-container-low": "#f0f3ff",
                      "primary-fixed": "#dce1ff",
                      "on-primary": "#ffffff",
                      "surface-bright": "#f9f9ff",
                      "parent-rational": "#10B981",
                      "secondary-fixed-dim": "#ffb68b",
                      "inverse-surface": "#263143",
                      "on-secondary-fixed-variant": "#753400",
                      "tertiary-container": "#006d4a",
                      "parent-observing": "#718096",
                      "tertiary-fixed-dim": "#4edea3",
                      "mascot-gold": "#FF9F1C",
                      "primary": "#003bb2",
                      "surface-variant": "#d8e3fb",
                      "error": "#ba1a1a",
                      "on-primary-fixed": "#00164f",
                      "surface-container-lowest": "#ffffff",
                      "on-tertiary": "#ffffff",
                      "surface-bg": "#F8FAFC",
                      "surface-dim": "#cfdaf2",
                      "parent-anxious": "#FF7A00",
                      "failure-red": "#EF4444",
                      "on-secondary-container": "#592600",
                      "surface-tint": "#1d52d9",
                      "surface-container-highest": "#d8e3fb",
                      "on-primary-container": "#cfd7ff",
                      "tertiary": "#005237",
                      "on-error": "#ffffff",
                      "secondary": "#994700",
                      "inverse-on-surface": "#ecf1ff",
                      "on-secondary": "#ffffff",
                      "on-surface": "#111c2d",
                      "secondary-fixed": "#ffdbc8",
                      "on-error-container": "#93000a",
                      "surface-container": "#e7eeff",
                      "surface": "#f9f9ff",
                      "surface-container-high": "#dee8ff",
                      "outline": "#747686",
                      "on-background": "#111c2d",
                      "on-tertiary-fixed": "#002113",
                      "primary-fixed-dim": "#b6c4ff",
                      "on-secondary-fixed": "#321200",
                      "error-container": "#ffdad6",
                      "background": "#f9f9ff",
                      "primary-container": "#1e52d9",
                      "outline-variant": "#c4c5d7",
                      "on-primary-fixed-variant": "#003ab1",
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
42
43
44
45
46
47
48
49
50
51
52
53
54


                      "inverse-primary": "#b6c4ff",
                      "on-tertiary-container": "#65f2b5",
                      "parent-confused": "#00B2FF",
                      "tertiary-fixed": "#6ffbbe",
                      "secondary-container": "#fb7800",
                      "on-surface-variant": "#434654"
              },
              "borderRadius": {
                      "DEFAULT": "0.25rem",
                      "lg": "0.5rem",
                      "xl": "0.75rem",
                      "full": "9999px"
              },
              "spacing": {
                      "stack-sm": "8px",
                      "stack-md": "16px",
                      "unit": "8px",
                      "container-margin": "24px",
                      "card-padding": "16px",
                      "gutter": "16px"
              },
              "fontFamily": {
                      "headline-md": [
                              "Hanken Grotesk"
                      ],
                      "headline-lg-mobile": [
                              "Hanken Grotesk"
                      ],
                      "body-lg": [
                              "Inter"
                      ],
                      "body-base": [
                              "Inter"
                      ],
                      "label-caps": [
                              "Inter"
                      ],
                      "headline-lg": [
                              "Hanken Grotesk"
                      ],
                      "annotation-italic": [
                              "Inter"
                      ]
              },
              "fontSize": {
                      "headline-md": [
                              "20px",
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
71
72
73
74
75
76
77
78
79
80
81
82
83
84
85
86
87
88
89
90
91
92
93
94
95
96
97
98
99
100
101


                              {
                                      "lineHeight": "28px",
                                      "fontWeight": "600"
                              }
                      ],
                      "headline-lg-mobile": [
                              "24px",
                              {
                                      "lineHeight": "32px",
                                      "fontWeight": "700"
                              }
                      ],
                      "body-lg": [
                              "16px",
                              {
                                      "lineHeight": "24px",
                                      "fontWeight": "400"
                              }
                      ],
                      "body-base": [
                              "14px",
                              {
                                      "lineHeight": "22px",
                                      "fontWeight": "400"
                              }
                      ],
                      "label-caps": [
                              "12px",
                              {
                                      "lineHeight": "16px",
                                      "letterSpacing": "0.05em",
                                      "fontWeight": "600"
                              }
                      ],
                      "headline-lg": [
                              "32px",
                              {
                                      "lineHeight": "40px",
                                      "fontWeight": "700"
                              }
                      ],
                      "annotation-italic": [
                              "12px",
                              {
                                      "lineHeight": "16px",
                                      "fontWeight": "400"
                              }
102
103
104
105
106
107
108
109
110
111
112
113
114
115
116
117
118
119
120
121
122
123
124
125
126
127
128
129
130
131
132
133
134
135
136
137
138
139
140
141
142
143
144
145
146
147
148


                      ]
              }
      },
          },
        }
      </script>
② Custom CSS 样式
代码块

        body { font-family: 'Inter', sans-serif; }
        h1, h2, h3, h4, h5, h6, .font-headline-md, .font-headline-lg { font-
family: 'Hanken Grotesk', sans-serif; }

        /* Waveform Animation */
        @keyframes wave {
            0%, 100% { height: 8px; }
            50% { height: 24px; }
        }
        .waveform-bar {
            animation: wave 1.2s infinite ease-in-out;
            transform-origin: bottom;
        }
        .waveform-bar:nth-child(1) { animation-delay: 0.0s; }
        .waveform-bar:nth-child(2) { animation-delay: 0.1s; }
        .waveform-bar:nth-child(3) { animation-delay: 0.2s; }
        .waveform-bar:nth-child(4) { animation-delay: 0.3s; }
        .waveform-bar:nth-child(5) { animation-delay: 0.4s; }
        .waveform-bar:nth-child(6) { animation-delay: 0.5s; }
        .waveform-bar:nth-child(7) { animation-delay: 0.6s; }
        .waveform-bar:nth-child(8) { animation-delay: 0.7s; }

        /* Pulse Animation */
        @keyframes pulse-ring {
            0% { transform: scale(0.8); opacity: 0.5; }
            100% { transform: scale(1.3); opacity: 0; }
        }
        .pulse-ring::before {
            content: '';
            position: absolute;
            left: 0; top: 0; right: 0; bottom: 0;
            border-radius: 50%;
            border: 2px solid theme('colors.primary');
149
150
151
152
153
154
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33


            animation: pulse-ring 2s infinite cubic-bezier(0.215, 0.61, 0.355, 
1);
        }

③ Navigation 顶部导航栏
代码块
<nav class="bg-[#FF9F1C] text-on-secondary-fixed dark:bg-inverse-surface h-
full w-64 fixed left-0 top-0 overflow-y-auto shadow-sm dark:shadow-none flex 
flex-col p-stack-md shrink-0 border-r border-mascot-gold/20 z-50">
<!-- Brand/Header -->
<div class="flex items-center gap-3 mb-8 px-2">
<div class="w-10 h-10 rounded-full bg-primary-container flex items-center 
justify-center shrink-0">
<span class="material-symbols-outlined text-on-primary-container">school</span>
</div>
<div>
<h2 class="font-headline-md text-headline-md font-bold text-primary dark:text-
inverse-primary truncate">Master Liu</h2>
<p class="font-body-base text-body-base text-on-surface-variant truncate">AI 
Sales Mentor</p>
</div>
</div>
<!-- Main Tabs -->
<div class="flex-1 flex flex-col gap-1"><a class="flex items-center gap-3 px-4 
py-3 rounded-lg text-on-secondary-fixed hover:bg-white/20 transition-colors 
duration-200" href="#">
<span class="material-symbols-outlined">menu_book</span>
<span class="font-body-base text-body-base font-semibold">场景库</span>
</a>
<a class="flex items-center gap-3 px-4 py-3 rounded-lg text-on-secondary-fixed 
font-bold border-r-4 border-on-secondary-fixed bg-white/20 transition-
transform duration-150 scale-95" href="#">
<span class="material-symbols-outlined" style="font-variation-settings: 'FILL' 
1;">person_search</span>
<span class="font-body-base text-body-base font-semibold">角色库</span>
</a>
<a class="flex items-center gap-3 px-4 py-3 rounded-lg text-on-secondary-fixed 
hover:bg-white/20 transition-colors duration-200" href="#">
<span class="material-symbols-outlined">history</span>
<span class="font-body-base text-body-base font-semibold">对练历史</span>
</a>
<a class="flex items-center gap-3 px-4 py-3 rounded-lg text-on-secondary-fixed 
hover:bg-white/20 transition-colors duration-200" href="#">
34
35
36
1
2
3
4
5
6
7
8
9
10
11
12
13
14
15
16
17
18
19
20
21
22
23
24
25


<span class="material-symbols-outlined">dashboard</span>
<span class="font-body-base text-body-base font-semibold">团队看板</span>
</a></div>
<!-- Footer Actions -->
<div class="mt-auto pt-4 border-t border-surface-container flex flex-col gap-
1">
<button class="w-full py-3 px-4 bg-primary text-on-primary rounded-full font-
label-caps text-label-caps hover:opacity-90 transition-opacity shadow-sm mb-4">
定制企业专属看板</button>
<a class="flex items-center gap-3 px-4 py-2 rounded-lg text-on-surface-variant 
hover:bg-surface-container-high transition-colors" href="#">
<span class="material-symbols-outlined">settings</span>
<span class="font-body-base text-body-base">设置</span>
</a>
<a class="flex items-center gap-3 px-4 py-2 rounded-lg text-on-surface-variant 
hover:bg-surface-container-high transition-colors" href="#">
<span class="material-symbols-outlined">help</span>
<span class="font-body-base text-body-base">帮助与支持</span>
</a>
</div>
</nav>
④ Practice Canvas 对练画布
代码块
</nav>
<!-- Main Content Area -->
<main class="ml-64 flex-1 flex flex-col h-full bg-[#1e52d9] relative text-
white">
<!-- TopAppBar Context -->
<header class="h-16 bg-[#1e52d9] border-b border-white/10 flex justify-between 
items-center px-container-margin shrink-0 shadow-sm z-40">
<div class="flex items-center gap-4">
<div class="flex items-center gap-2 bg-surface-container px-3 py-1.5 rounded-
md">
<span class="material-symbols-outlined text-outline text-
sm">movie_filter</span>
<span class="font-label-caps text-label-caps text-on-surface">训练: S-01 破冰
</span>
</div>
<div class="flex items-center gap-2 bg-parent-anxious/10 px-3 py-1.5 rounded-
md border border-parent-anxious/20">
<span class="material-symbols-outlined text-parent-anxious text-sm">face</span>
<span class="font-label-caps text-label-caps text-parent-anxious">对象: 张宝妈 
(焦虑型家长)</span>
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40
41
1
2
3
4
5
6
7
8
9
10
11
12
13


</div>
</div>
<div class="flex items-center gap-4">
<div class="flex items-center gap-2 text-white font-body-base text-body-base 
font-semibold">
<span class="material-symbols-outlined text-white/80">timer</span>
                    04:23
                </div>
<button class="px-4 py-2 bg-error/10 text-error hover:bg-error/20 rounded-full 
font-label-caps text-label-caps transition-colors flex items-center gap-2">
<span class="material-symbols-outlined text-sm">stop_circle</span>结束对话
</button>
</div>
</header>
<!-- Training Canvas Layout -->
<div class="flex-1 flex overflow-hidden">
<!-- Center Stage (Avatar & Interaction) -->
<div class="flex-1 flex flex-col relative">
<!-- 3D Avatar Area -->
<div class="flex-1 flex flex-col items-center justify-center p-8 relative">
<!-- Subtle background glow behind avatar -->
<div class="absolute inset-0 flex items-center justify-center opacity-30 
pointer-events-none">
<div class="w-96 h-96 bg-primary-fixed rounded-full blur-3xl"></div>
</div>
<div class="relative w-72 h-72 mb-8 z-10 flex items-center justify-center">
<img alt="P-01 Anxious Parent 3D Avatar" class="w-64 h-64 object-cover rounded-
full shadow-2xl border-4 border-surface-bright object-top" data-alt="A highly 
detailed 3D render of an anthropomorphic cat character wearing a beige 
professional suit and a floral scarf, acting as an 'Anxious Parent'. The cat 
has large, expressive, slightly worried eyes framed by round tortoiseshell 
glasses. The lighting is soft and professional, typical of a high-end 
corporate training application, set against a clean, light studio background 
to emphasize the character. The mood is tense but approachable." 
src="https://lh3.googleusercontent.com/aida/ADBb0ujtodUvUVt7GCpiBPHexAlVMsXVh2_
BzsMy6fzL0dzijwzvFROCdl5orj-kQYAQhr_U34cFVtZjce3AbJfoqJh5NnIxA3d1MRrme-
6x3Re_PJkDQ0zmaf0M9nLuF9t-4wTiTYOsw2K7HRgAtGkvjuYiq0DxxsoqKNfNa7y-dc-
C1VMwdZCbp9uMz6nI-_f3pp-6QuGdcuqTgHzqXS0ACU4QDy_-
VI7IlKgYmQhT30vaqNhjUPYa7l3zgrs"/>
<!-- Emotion Indicator Badge -->
<div class="absolute -bottom-2 right-4 bg-surface-bright rounded-full p-2 
shadow-xl border border-surface-container flex items-center gap-2 pr-4">
<div class="w-8 h-8 rounded-full bg-parent-anxious/20 flex items-center 
justify-center">
<span class="material-symbols-outlined text-parent-
anxious">sentiment_worried</span>
</div>
14
15
16
17
18
19
20
21
22
23
24
25
26
27
28
29
30
31
32
33
34
35
36
37
38
39
40


<span class="font-label-caps text-label-caps text-on-surface font-bold">焦虑
</span>
</div>
</div>
<!-- Meters -->
<div class="w-full max-w-md bg-surface-bright p-4 rounded-xl shadow-md border 
border-surface-container-low z-10">
<div class="flex justify-between items-center mb-2">
<span class="font-label-caps text-label-caps text-on-surface-variant">耐心值
</span>
<span class="font-label-caps text-label-caps text-parent-anxious font-bold">45%
</span>
</div>
<div class="w-full h-2 bg-surface-container-high rounded-full overflow-hidden">
<div class="h-full bg-parent-anxious rounded-full transition-all duration-500" 
style="width: 45%;"></div>
</div>
</div>
</div>
<!-- Bottom Interaction Zone (Transcript & Voice) -->
<div class="h-1\/3 min-h-[300px] bg-[#1e52d9]/90 backdrop-blur-md border-t 
border-white/10 flex flex-col shadow-[0_-4px_20px_rgba(0,0,0,0.2)] z-20">
<!-- Transcript Area -->
<div class="flex-1 overflow-y-auto p-container-margin flex flex-col gap-6">
<!-- AI Bubble -->
<div class="flex items-start gap-4 max-w-[80%]">
<div class="w-10 h-10 rounded-full bg-parent-anxious/20 flex items-center 
justify-center shrink-0 border border-parent-anxious/30 mt-1 shadow-sm">
<span class="material-symbols-outlined text-parent-anxious">face</span>
</div>
<div class="bg-surface-bright p-4 rounded-2xl rounded-tl-none border border-
surface-container shadow-sm">
<p class="font-body-lg text-[15px] leading-relaxed text-on-surface">"我真的很担心
我儿子的注意力。他花了太多时间在游戏上，成绩也下滑了。我不知道再来一个项目是否只会让他分
心。"</p>
</div>
</div>
<!-- User Bubble -->
<div class="flex items-start gap-4 max-w-[80%] self-end flex-row-reverse">
<div class="w-10 h-10 rounded-full bg-primary/20 flex items-center justify-
center shrink-0 border border-primary/30 mt-1 shadow-sm">
<span class="material-symbols-outlined text-white">person</span>
</div>
<div class="bg-primary text-on-primary p-4 rounded-2xl rounded-tr-none shadow-
md">
<p class="font-body-lg text-[15px] leading-relaxed">"我非常理解您的顾虑。当孩子成绩
已经让人压力很大时，担心分心是很正常的..."</p>
41
42
43
44
45
46
47
48
49
50
51
52
53
54
55
56
57
58
59
60
61
62
63
64
65
66
67
68
69
70
71
72
73
74


</div>
</div>
</div>
<!-- Voice Input Area -->
<div class="p-4 border-t border-white/10 flex items-center gap-4 bg-[#1a46b8]">
<button class="w-12 h-12 rounded-full bg-white text-primary flex items-center 
justify-center shadow-lg hover:bg-white/90 transition-colors shrink-0 relative 
pulse-ring">
<span class="material-symbols-outlined">mic</span>
</button>
<div class="flex-1 flex items-center gap-1 h-12 bg-white/10 rounded-full px-6 
border border-white/20">
<!-- Animated Waveform -->
<div class="flex items-end gap-1 h-6 w-32">
<div class="w-1.5 bg-white rounded-t-sm waveform-bar"></div>
<div class="w-1.5 bg-white rounded-t-sm waveform-bar"></div>
<div class="w-1.5 bg-white rounded-t-sm waveform-bar"></div>
<div class="w-1.5 bg-white rounded-t-sm waveform-bar"></div>
<div class="w-1.5 bg-white rounded-t-sm waveform-bar"></div>
<div class="w-1.5 bg-white rounded-t-sm waveform-bar"></div>
<div class="w-1.5 bg-white rounded-t-sm waveform-bar"></div>
<div class="w-1.5 bg-white rounded-t-sm waveform-bar"></div>
</div>
<span class="font-body-base text-[15px] text-white/80 ml-4 italic">正在倾听...
</span>
</div>
<button class="p-3 text-white hover:bg-white/10 rounded-full transition-
colors">
<span class="material-symbols-outlined">keyboard</span>
</button>
</div>
</div>
</div>
<!-- Right Sidebar: Master Liu Mentor Panel -->
<div class="w-[360px] bg-surface-bg text-on-surface border-l border-surface-
container flex flex-col shadow-[-4px_0_20px_rgba(0,0,0,0.1)] z-30 overflow-y-
auto">
<!-- Mentor Header -->
<div class="p-6 border-b border-surface-container flex flex-col items-center 
bg-gradient-to-b from-surface-container-low to-surface-bright shrink-0">
<img alt="Master Liu Squirrel Mascot" class="w-24 h-24 object-contain mb-3 
drop-shadow-md" data-alt="A 3D render of a cute anthropomorphic squirrel 
acting as a teacher or mentor. The squirrel wears round glasses, a white 
collared shirt with a red bowtie, and a blue patterned vest. It is holding a 
wooden pointer stick in one hand and a stack of classic hardcover books under 
the other arm. The lighting is bright and studio-like, set against a warm 
beige background, typical of a high-end educational SaaS platform's gamified 
75
76
77
78
79
80
81
82
83
84
85
86
87
88
89
90
91
92
93
94
95
96
97
98
99
100
101
102
103
104
105
106
107


mascot." 
src="https://lh3.googleusercontent.com/aida/ADBb0uj8TuiAgS9y8yo4zD_Azu8mnDVCkdc
5ENHhK3-AQCNuRIPn4SrCXdG8nr53RTBA_OC_EDCl79Od7-d5OMgEAvMp2TQcygsx2XESub-
sRsHMFbB-
bbSYHyYbCnZPG9XdRi_1dcQSrNR3xbokzfjqo0SApaLCHGXXWRotPME_hvAAvFDnxYW7WLDpQ_tspPL
06PFxAL-n8y0rRhRX6mYAWwi-KSNLFgDeZmjTCOQbFFNYfaREBKusZoMhJKc"/>
<h3 class="font-headline-md text-headline-md font-bold text-on-surface text-
center">Master Liu</h3>
<div class="flex items-center gap-1 text-primary mt-1">
<span class="material-symbols-outlined text-sm">wifi_tethering</span>
<span class="font-label-caps text-label-caps">正在分析语境</span>
</div>
</div>
<div class="p-6 flex flex-col gap-6 flex-1">
<!-- Master's Tip Alert -->
<div class="bg-mascot-gold/10 border border-mascot-gold/30 rounded-xl p-5 
shadow-sm relative shrink-0">
<div class="absolute -top-3 -left-2 bg-surface-bright rounded-full p-1.5 
border border-surface-container shadow-sm">
<span class="material-symbols-outlined text-mascot-gold text-
xl">lightbulb</span>
</div>
<h4 class="font-label-caps text-[13px] text-secondary font-bold mb-2 ml-5">刘总
支招</h4>
<p class="font-body-base text-[15px] leading-relaxed text-on-surface">"不要急着
推销产品，先关注她的焦虑。她需要感觉到被理解，才会倾听你的建议。"</p>
</div>
<!-- Skill Hints Card -->
<div class="bg-surface-container-lowest border border-primary/20 rounded-xl 
shadow-md flex flex-col flex-1">
<div class="bg-primary-container/10 px-5 py-4 border-b border-primary/10 flex 
justify-between items-center shrink-0">
<span class="font-label-caps text-[13px] text-primary font-bold flex items-
center gap-2"><span class="material-symbols-outlined text-
base">psychology</span> 目标技巧</span>
<span class="bg-primary text-on-primary font-label-caps text-[11px] px-3 py-1 
rounded-full shadow-sm">SK-01 Empathy</span>
</div>
<div class="p-6 flex flex-col gap-5 overflow-y-auto">
<!-- Step 1: Completed -->
<div class="flex items-start gap-4 opacity-60">
<div class="mt-0.5 w-6 h-6 rounded-full bg-parent-rational text-on-primary 
flex items-center justify-center shrink-0 shadow-sm">
<span class="material-symbols-outlined text-[16px]">check</span>
</div>
<div>
108
109
110
111
112
113
114
115
116
117
118
119
120
121
122
123
124
125
126
127
128
129
130
131
132
133
134
135


<p class="font-body-base text-[15px] font-semibold text-on-surface line-
through decoration-outline">1. 承认感受</p>
</div>
</div>
<!-- Step 2: Active -->
<div class="flex items-start gap-4 bg-primary-fixed/30 p-3 -mx-3 rounded-lg 
border border-primary/20 shadow-sm">
<div class="mt-0.5 w-6 h-6 rounded-full border-2 border-primary flex items-
center justify-center shrink-0 bg-white">
<div class="w-2.5 h-2.5 bg-primary rounded-full animate-pulse"></div>
</div>
<div>
<p class="font-body-base text-[16px] font-bold text-primary">2. 共情安抚</p>
<p class="font-annotation-italic text-[13px] text-on-surface-variant mt-
1.5">"这种担心是很正常的..."</p>
</div>
</div>
<!-- Step 3: Pending -->
<div class="flex items-start gap-4 opacity-50">
<div class="mt-0.5 w-6 h-6 rounded-full border-2 border-outline flex items-
center justify-center shrink-0">
<span class="text-[12px] font-bold text-outline">3</span>
</div>
<div>
<p class="font-body-base text-[15px] font-semibold text-on-surface">3. 开放式挖
掘</p>
</div>
</div>
<!-- Step 4: Pending -->
<div class="flex items-start gap-4 opacity-50">
<div class="mt-0.5 w-6 h-6 rounded-full border-2 border-outline flex items-
center justify-center shrink-0">
<span class="text-[12px] font-bold text-outline">4</span>
</div>
<div>
<p class="font-body-base text-[15px] font-semibold text-on-surface">4. 引导解决
方案</p>
</div>
</div>
</div>
</div>
</div>
</div>
</div>

136
137
138
139
140
141
142
143
144
145
146
147
148
149
150
151
152
153
154
155
156
157
158
159
160
161
162
163
164
165
166
167
168
169
170
171
172