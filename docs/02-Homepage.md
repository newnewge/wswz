# 模块二：首页（Homepage）

> 来源: 飞书文档「前端代码-松鼠ai培训助手前端界面」
> 模块: 首页 · Module 2/9

---

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


文件：index.html · 深色主题（surface-bg: #001a4d + 金橙 secondary: #FF9F1C）
① Tailwind Config 色板配置
代码块
<script id="tailwind-config">
        tailwind.config = {
          darkMode: "class",
          theme: {
            extend: {
              "colors": {
                      "surface-bg": "#001a4d",
                      "on-surface": "#ffffff",
                      "primary-fixed-dim": "#b6c4ff",
                      "on-secondary": "#ffffff",
                      "failure-red": "#EF4444",
                      "on-error-container": "#93000a",
                      "on-tertiary-container": "#65f2b5",
                      "surface-container-highest": "#1a3a6d",
                      "mascot-gold": "#FF9F1C",
                      "on-primary-fixed-variant": "#003ab1",
                      "surface-container-low": "#002b66",
                      "error-container": "#ffdad6",
                      "inverse-surface": "#ecf1ff",
                      "primary-container": "#1e52d9",
                      "on-secondary-fixed": "#321200",
                      "secondary-fixed": "#ffdbc8",
                      "on-surface-variant": "#a3b2cc",
                      "tertiary-fixed": "#6ffbbe",
                      "on-secondary-container": "#592600",
                      "on-background": "#ffffff",
                      "secondary-fixed-dim": "#ffb68b",
                      "on-error": "#ffffff",
                      "on-primary-container": "#cfd7ff",
                      "secondary": "#ff9900",
                      "surface-bright": "#002359",
                      "outline-variant": "#2a4d8c",
                      "on-primary": "#ffffff",
                      "surface-container-high": "#113061",
                      "secondary-container": "#ff9900",
                      "surface-tint": "#1d52d9",
                      "primary": "#3b82f6",
                      "surface-variant": "#1a3a6d",
                      "parent-anxious": "#FF7A00",
                      "surface": "#002359",
                      "on-tertiary-fixed-variant": "#005236",
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
34
35
36
37
38
39
40
41


                      "tertiary-container": "#006d4a",
                      "tertiary-fixed-dim": "#4edea3",
                      "on-primary-fixed": "#00164f",
                      "primary-fixed": "#dce1ff",
                      "parent-rational": "#10B981",
                      "on-tertiary-fixed": "#002113",
                      "surface-container-lowest": "#001133",
                      "inverse-on-surface": "#001a4d",
                      "on-tertiary": "#ffffff",
                      "on-secondary-fixed-variant": "#753400",
                      "background": "#001a4d",
                      "surface-container": "#ff9900",
                      "outline": "#5c78a3",
                      "parent-confused": "#00B2FF",
                      "inverse-primary": "#b6c4ff",
                      "parent-observing": "#718096",
                      "error": "#ba1a1a",
                      "surface-dim": "#00153d",
                      "tertiary": "#005237"
              },
              "borderRadius": {
                      "DEFAULT": "0.25rem",
                      "lg": "0.5rem",
                      "xl": "0.75rem",
                      "full": "9999px"
              },
              "spacing": {
                      "container-margin": "24px",
                      "stack-md": "16px",
                      "gutter": "16px",
                      "stack-sm": "8px",
                      "card-padding": "16px",
                      "unit": "8px"
              },
              "fontFamily": {
                      "body-base": ["Inter", "system-ui", "sans-serif"],
                      "headline-lg": ["Hanken Grotesk", "sans-serif"],
                      "headline-md": ["Hanken Grotesk", "sans-serif"],
                      "label-caps": ["Inter", "sans-serif"]
              }
            }
          }
        }
    </script>
② Custom CSS 样式
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


代码块

        .perspective-1000 { perspective: 1000px; }
        .transform-style-3d { transform-style: preserve-3d; }
        .backface-hidden { backface-visibility: hidden; }
        .rotate-y-180 { transform: rotateY(180deg); }
        .group:hover .group-hover\:rotate-y-180 { transform: rotateY(180deg); }

        /* Game-style card background for scenario library */
        .scenario-card-bg {
            background: linear-gradient(135deg, #1a3a6d 0%, #002359 100%);
            border: 2px solid #2a4d8c;
            box-shadow: inset 0 0 15px rgba(59, 130, 246, 0.2), 0 4px 6px 
rgba(0, 0, 0, 0.3);
        }
        .sidebar-active {
            background-color: rgba(255, 255, 255, 0.2);
            color: white;
        }

③ Navigation 侧边导航栏
代码块
<nav class="bg-surface-container border-r border-orange-600 docked full-height 
left-0 w-72 fixed top-0 h-full z-40 flex flex-col p-4 shadow-xl">
<div class="flex flex-col gap-4 mb-8">
<div class="w-full flex items-center justify-center py-4 overflow-hidden"><img 
alt="Brand Logo" class="w-44 h-auto object-contain" 
src="https://lh3.googleusercontent.com/aida-
public/AB6AXuBl3onU7hwPsi3F26mGjk0NkFa6uBuknscchnsrjcbyvyV8oNBZXCltIEmuxPMZ4oL0
k2hicGu1NYn86ymTkDhQl_WdViQoTrIV3PbLF4rotLj0NBhDQG6z7UBD-
nzis0svrSqTB9rH0uBE56dtwmpj3fJMIwAiNyjbA7z1Jq5khM00IqDdUFlUrGgW1dVvcDIYBaZNOQvz
TNrmaLMipGfQmlNw91YwyZ0QqJrofF74jtWkATDNNDTnu4grX4uqwXJLXzDVhMNSWuKq"></div>
<div>
<h1 class="font-headline-md font-bold text-white leading-tight text-headline-
lg tracking-widest">           销冠进阶计划</h1>
<p class="font-annotation-italic text-[12px] text-white/80">                  
Master Liu 导师模式</p>
</div>
</div>
<button class="w-full bg-white text-secondary rounded-lg py-3 mb-8 font-bold 
text-label-caps flex items-center justify-center gap-2 hover:bg-orange-50 
transition-colors shadow-lg">
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
1
2
3
4
5
6
7
8
9


<span class="material-symbols-outlined" style="font-variation-settings: "FILL" 
1;">add_circle</span>
        开始新对练
    </button>
<div class="flex flex-col gap-2 flex-1">
<a class="flex items-center gap-3 px-4 py-3 text-white hover:bg-white/10 
rounded-lg transition-all" href="#">
<span class="material-symbols-outlined">menu_book</span>
            场景库
        </a>
<a class="flex items-center gap-3 px-4 py-3 text-white hover:bg-white/10 
rounded-lg transition-all" href="#">
<span class="material-symbols-outlined">person_search</span>
            角色库
        </a>
<a class="flex items-center gap-3 px-4 py-3 text-white hover:bg-white/10 
rounded-lg transition-all" href="#">
<span class="material-symbols-outlined">history</span>
            对练历史
        </a>
<a class="flex items-center gap-3 px-4 py-3 sidebar-active rounded-lg font-
bold" href="#">
<span class="material-symbols-outlined">analytics</span>
            团队看板
        </a>
</div>
<div class="flex flex-col gap-2 mt-auto pt-4 border-t border-white/20">
<a class="flex items-center gap-3 px-4 py-3 text-white/90 hover:bg-white/10 
rounded-lg" href="#">
<span class="material-symbols-outlined text-[20px]">settings</span>
            设置
        </a>
<a class="flex items-center gap-3 px-4 py-3 text-white/90 hover:bg-white/10 
rounded-lg" href="#">
<span class="material-symbols-outlined text-[20px]">help</span>
            帮助
        </a>
</div>
</nav>
④ Main Content 主要内容区
代码块
</nav>
<!-- Main Content -->
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
1
2


<main class="flex-1 ml-72 p-container-margin flex flex-col gap-container-
margin">
<!-- Welcome Banner Bento -->
<section class="bg-surface rounded-xl p-8 border border-outline-variant shadow-
lg flex items-center justify-between relative overflow-hidden">
<div class="absolute inset-0 bg-gradient-to-r from-primary/10 to-transparent 
pointer-events-none"></div>
<div class="relative z-10 max-w-2xl">
<h2 class="font-headline-lg text-headline-lg text-on-surface mb-2">欢迎回到竞技
场。</h2>
<p class="font-body-lg text-body-lg text-on-surface-variant mb-6">AI刘总 
(Master Liu) 建议你今天挑战一个高难度的家长互动。本周你的共情能力评分提升了12%！</p>
<div class="bg-surface-container-low rounded-lg p-4 inline-flex items-center 
gap-4 border border-outline-variant shadow-inner">
<div class="flex items-center justify-center w-12 h-12 bg-secondary text-white 
rounded-full shadow-lg">
<span class="material-symbols-outlined" style="font-variation-settings: "FILL" 
1;">emoji_events</span>
</div>
<div>
<p class="font-label-caps text-label-caps text-on-surface-variant uppercase 
tracking-wider">Master Liu 推荐挑战</p>
<p class="font-headline-md text-headline-md text-on-surface">安抚迷茫型家长 (P-
02)</p>
</div>
<button class="ml-4 px-6 py-2 bg-secondary text-white rounded-lg font-bold 
hover:scale-105 transition-transform shadow-md">立即开战</button>
</div>
</div>
<div class="relative z-10 w-48 h-48 flex-shrink-0 bg-transparent">
<img alt="Master Liu Mascot" class="w-full h-full object-contain drop-shadow-
2xl bg-transparent" src="https://lh3.googleusercontent.com/aida-
public/AB6AXuDdABdTG3jvxbVUqO-RHI71G5-
gs5OeSqEETXex4_ReNe4x5ZpJI6x5xzexTKfYioX27qdy96B63upV99oybKRhQtqCLXQc9uGazMr0cA
aeRQKnyGMapyZ6ZujDnr0txek7QsZ4yEEfSMPgOqArlPJXhTglVME17vLx6uVDn5V-
7oGxj1qu8l2tB-E3iRVZptCw8AVJHbogSLdkbHuZ7KkSAuywtAPmpW-
hNrEKIInHbE7pE84_BJAL1dWyGUpOPlNdFJCW7134CWtu">
</div>
</section>
<div class="grid grid-cols-12 gap-gutter">
<!-- Scenario Library (Left Column - 7 cols) -->
<section class="col-span-7 flex flex-col gap-stack-md">
<div class="flex items-center justify-between mb-2">
<h3 class="font-headline-md text-headline-md text-on-surface flex items-center 
gap-2">
<span class="material-symbols-outlined text-
secondary">collections_bookmark</span>
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


                    实战场景库
                </h3>
<a class="text-secondary font-bold text-body-base hover:underline" href="#">查看
全部副本</a>
</div>
<div class="grid grid-cols-2 gap-gutter">
<!-- Scenario S-01 -->
<div class="scenario-card-bg rounded-lg p-card-padding transition-all hover:-
translate-y-1 cursor-pointer group">
<div class="flex items-center justify-between mb-4 pb-3 border-b border-
white/10">
<span class="bg-secondary/20 text-secondary border border-secondary/30 font-
label-caps text-[10px] px-2 py-0.5 rounded">难度: 初级</span>
<div class="flex text-mascot-gold">
<span class="material-symbols-outlined text-[16px]" style="font-variation-
settings: "FILL" 1;">star</span>
<span class="material-symbols-outlined text-[16px]" style="font-variation-
settings: "FILL" 1;">star</span>
<span class="material-symbols-outlined text-[16px]">star</span>
</div>
</div>
<h4 class="font-headline-md text-headline-md text-white mb-2">破冰接待</h4>
<p class="text-on-surface-variant text-[13px] mb-4">目标：在5分钟内通过共情建立信
任，锁定核心痛点。</p>
<div class="flex flex-col gap-2">
<div class="flex items-center gap-2 text-on-surface-variant text-body-base">
<span class="material-symbols-outlined text-[18px] text-
secondary">check_circle</span>
<span class="">建立初步信任</span>
</div>
</div>
</div>
<!-- Scenario S-02 -->
<div class="scenario-card-bg rounded-lg p-card-padding transition-all hover:-
translate-y-1 cursor-pointer group">
<div class="flex items-center justify-between mb-4 pb-3 border-b border-
white/10">
<span class="bg-red-500/20 text-red-400 border border-red-500/30 font-label-
caps text-[10px] px-2 py-0.5 rounded">难度: 专家</span>
<div class="flex text-mascot-gold">
<span class="material-symbols-outlined text-[16px]" style="font-variation-
settings: "FILL" 1;">star</span>
<span class="material-symbols-outlined text-[16px]" style="font-variation-
settings: "FILL" 1;">star</span>
<span class="material-symbols-outlined text-[16px]" style="font-variation-
settings: "FILL" 1;">star</span>
</div>
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
55
56
57
58
59
60
61
62
63


</div>
<h4 class="font-headline-md text-headline-md text-white mb-2">产品价值推荐</h4>
<p class="text-on-surface-variant text-[13px] mb-4">目标：深度解析MCM教学法，转化理
智型家长。</p>
<div class="flex flex-col gap-2">
<div class="flex items-center gap-2 text-on-surface-variant text-body-base">
<span class="material-symbols-outlined text-[18px] text-
outline">radio_button_unchecked</span>
<span class="">讲解MCM逻辑</span>
</div>
</div>
</div>
</div>
</section>
<!-- Role Library (Right Column - 5 cols) -->
<section class="col-span-5 flex flex-col gap-stack-md">
<div class="flex items-center justify-between mb-2">
<h3 class="font-headline-md text-headline-md text-on-surface flex items-center 
gap-2">
<span class="material-symbols-outlined text-secondary">groups</span>
                    家长图鉴库
                </h3>
<span class="text-on-surface-variant font-annotation-italic text-[12px]">悬停查
看攻略</span>
</div>
<div class="flex flex-col gap-4 perspective-1000">
<!-- P-01 Anxious -->
<div class="relative w-full h-28 group cursor-pointer">
<div class="w-full h-full absolute transition-transform duration-500 transform-
style-3d group-hover:rotate-y-180 shadow-lg rounded-xl">
<!-- Front -->
<div class="absolute w-full h-full backface-hidden bg-[#ff7a00]/10 border 
border-[#ff7a00]/30 rounded-xl p-4 flex items-center gap-4">
<div class="w-16 h-16 rounded-full border-2 border-parent-anxious bg-surface 
overflow-hidden flex-shrink-0">
<img alt="Anxious Parent" class="w-full h-full object-cover" 
src="https://lh3.googleusercontent.com/aida/ADBb0ujtodUvUVt7GCpiBPHexAlVMsXVh2_
BzsMy6fzL0dzijwzvFROCdl5orj-kQYAQhr_U34cFVtZjce3AbJfoqJh5NnIxA3d1MRrme-
6x3Re_PJkDQ0zmaf0M9nLuF9t-4wTiTYOsw2K7HRgAtGkvjuYiq0DxxsoqKNfNa7y-dc-
C1VMwdZCbp9uMz6nI-_f3pp-6QuGdcuqTgHzqXS0ACU4QDy_-
VI7IlKgYmQhT30vaqNhjUPYa7l3zgrs">
</div>
<div>
<div class="flex items-center gap-2 mb-1">
<h4 class="font-headline-md text-headline-md text-on-surface">焦虑型家长</h4>
<span class="bg-parent-anxious text-white text-[10px] px-1.5 py-0.5 rounded 
font-bold">LV.3</span>
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


</div>
<p class="text-[13px] text-on-surface-variant italic">“孩子再不进步就来不及了...”
</p>
</div>
</div>
<!-- Back -->
<div class="absolute w-full h-full backface-hidden bg-parent-anxious rounded-
xl p-4 rotate-y-180 flex flex-col justify-center">
<p class="font-bold text-white mb-1 flex items-center gap-1"><span 
class="material-symbols-outlined text-[18px]">psychology</span> 通关秘籍</p>
<p class="text-white/90 text-[12px]">使用共情回应 + 数据化提分方案。避免推销感。</p>
</div>
</div>
</div>
<!-- P-02 Confused -->
<div class="relative w-full h-28 group cursor-pointer">
<div class="w-full h-full absolute transition-transform duration-500 transform-
style-3d group-hover:rotate-y-180 shadow-lg rounded-xl">
<!-- Front -->
<div class="absolute w-full h-full backface-hidden bg-[#00b2ff]/10 border 
border-[#00b2ff]/30 rounded-xl p-4 flex items-center gap-4">
<div class="w-16 h-16 rounded-full border-2 border-parent-confused bg-surface 
overflow-hidden flex-shrink-0">
<img alt="Confused Parent" class="w-full h-full object-cover" 
src="https://lh3.googleusercontent.com/aida/ADBb0uj4Dw06TxBvUxvOeXR50kTaTaEpo-
nqRKL9YTzEZHk0CrPNqHkFiDVDr4GFhvNRohci4Wn6mvJ00G8kHfYlDvjZFqpnUsQY33okMC7wkAMBm
kbmAbz5Ix8dNK7RlA06EPXFRa8Y9wApNhLbo3nGmLoxTnAZIYM9QFeQVNYUqoyfmfdU-5-
Y3f4NSfAu99y5sIS8eOxH3Kgwldr3Ox4dwhLRCa15zWvwm5RukvefcwiR0ZgzgshIMZQ3Ip1-">
</div>
<div>
<div class="flex items-center gap-2 mb-1">
<h4 class="font-headline-md text-headline-md text-on-surface">迷茫型家长</h4>
<span class="bg-parent-confused text-white text-[10px] px-1.5 py-0.5 rounded 
font-bold">LV.2</span>
</div>
<p class="text-[13px] text-on-surface-variant italic">“AI怎么可能比真老师强？”</p>
</div>
</div>
<!-- Back -->
<div class="absolute w-full h-full backface-hidden bg-parent-confused rounded-
xl p-4 rotate-y-180 flex flex-col justify-center">
<p class="font-bold text-white mb-1 flex items-center gap-1"><span 
class="material-symbols-outlined text-[18px]">lightbulb</span> 逻辑重点</p>
<p class="text-white/90 text-[12px]">通过对比传统教学与AI自适应，突出效率差异。</p>
</div>
</div>
</div>
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


</div>
</section>
</div>
<!-- Content Divider -->
<div class="relative py-4 mt-4">
<div aria-hidden="true" class="absolute inset-0 flex items-center">
<div class="w-full border-t border-outline-variant"></div>
</div>
<div class="relative flex justify-center">
<span class="bg-surface-bg px-4 text-mascot-gold">
<span class="material-symbols-outlined text-[24px]" style="font-variation-
settings: "FILL" 1;">stars</span>
</span>
</div>
</div>
<!-- Weekly Sales Leaderboard Section -->
<section class="mt-2 pb-8">
<div class="flex items-center justify-between mb-6">
<h3 class="font-headline-md text-headline-md text-on-surface flex items-center 
gap-2">
<span class="material-symbols-outlined text-yellow-500" style="font-variation-
settings: "FILL" 1;">military_tech</span>
                年度累计训练排行
            </h3>
</div>
<div class="grid grid-cols-3 gap-6 max-w-5xl mx-auto items-end">
<!-- Runner Up -->
<div class="bg-surface-container-high rounded-xl p-4 border border-outline-
variant flex flex-col items-center text-center relative overflow-hidden h-48 
justify-center shadow-md">
<div class="absolute top-0 right-0 bg-slate-400 text-white px-2 py-0.5 text-
[10px] font-bold rounded-bl-lg">亚军</div>
<div class="w-14 h-14 rounded-full border-2 border-slate-300 p-0.5 mb-2">
<img alt="No.2" class="w-full h-full rounded-full object-cover" 
src="https://lh3.googleusercontent.com/aida/ADBb0uj8TuiAgS9y8yo4zD_Azu8mnDVCkdc
5ENHhK3-AQCNuRIPn4SrCXdG8nr53RTBA_OC_EDCl79Od7-d5OMgEAvMp2TQcygsx2XESub-
sRsHMFbB-
bbSYHyYbCnZPG9XdRi_1dcQSrNR3xbokzfjqo0SApaLCHGXXWRotPME_hvAAvFDnxYW7WLDpQ_tspPL
06PFxAL-n8y0rRhRX6mYAWwi-KSNLFgDeZmjTCOQbFFNYfaREBKusZoMhJKc">
</div>
<h5 class="font-bold text-white text-sm">王老师 (广州·越秀店)</h5>
<p class="text-secondary font-bold text-sm">1288 积分</p>
<div class="mt-1 px-2 py-0.5 bg-white/10 rounded-full text-[9px] text-
white/80">话术大师</div>
</div>
<!-- Champion -->
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


<div class="bg-gradient-to-b from-secondary/20 to-surface-container-high 
rounded-xl p-6 border-2 border-secondary flex flex-col items-center text-
center relative shadow-2xl h-56 justify-center">
<div class="absolute top-0 inset-x-0 flex justify-center -mt-5">
<span class="material-symbols-outlined text-secondary text-[40px]" style="font-
variation-settings: "FILL" 1;">workspace_premium</span>
</div>
<div class="w-16 h-16 rounded-full border-4 border-secondary p-0.5 mb-3 shadow-
orange-500/30 shadow-lg">
<img alt="Champion" class="w-full h-full rounded-full object-cover" 
src="https://lh3.googleusercontent.com/aida/ADBb0ugE73xlKFC4NGDBYvKvNjcCuqwrW3d
eBo9inOGUO7H1qANXElFnL2RqsKqgodnaRZ4DB12aS4ZtDKmknux8KsVcYPthzehYhBh4HeKP73motl
4ytN9O4v7UY2EnIW6xUPc5AJwc3axTGkvNtzaNUlMItMo6xZIoZiOqSlGTw07zYMnLuNZwZY8oyrhEx
v7zzrpKPccOOptM_nf1H9V63JnCg-UrK_8C9by83ndcMmIIPnJRPZK87zRq26xX">
</div>
<h5 class="font-headline-md font-bold text-white text-base">李经理 (广州·天河店)
</h5>
<p class="text-secondary text-lg font-black">210 课时</p>
<div class="mt-1 px-3 py-0.5 bg-secondary text-white rounded-full text-[10px] 
font-bold shadow-sm">学霸教练</div>
</div>
<!-- Third Place -->
<div class="bg-surface-container-high rounded-xl p-4 border border-outline-
variant flex flex-col items-center text-center relative overflow-hidden h-48 
justify-center shadow-md">
<div class="absolute top-0 right-0 bg-orange-800/80 text-white px-2 py-0.5 
text-[10px] font-bold rounded-bl-lg">季军</div>
<div class="w-14 h-14 rounded-full border-2 border-orange-800 p-0.5 mb-2">
<img alt="No.3" class="w-full h-full rounded-full object-cover" 
src="https://lh3.googleusercontent.com/aida/ADBb0ujroWHEZjDwI7Fp7y9MjTT96U36Szt
7F6OSb1iscLh4AQXfu9E4xyEOrxlc4EZUHlbuKToOIwt2YFJxe9_9Ig0grtWmrwSQafK-
hc3fild9311ggDUDK-
C2zo6VK7t7Rj_98GucrLcTd8wlM2CiFkDsGwJa59nMPQAbwPPj_LuFvsXZOR_V6UmifKXCN7LJ6vMAT
MquN5kq9H2YXqvydLqTAUIw_FC2VIUYWot3IOx8yivlLOMkUVw2XUiw">
</div>
<h5 class="font-bold text-white text-sm">张主管 (广州·海珠店)</h5>
<p class="text-secondary font-bold text-sm">950 积分</p>
<div class="mt-1 px-2 py-0.5 bg-white/10 rounded-full text-[9px] text-
white/80">潜力之星</div>
</div>
</div>
</section>