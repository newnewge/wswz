# 模块九：销冠技能库（Sales Champion Skills）

> 来源: 飞书文档「前端代码-松鼠ai培训助手前端界面」
> 模块: 销冠技能库 · Module 9/9

---

文件：sales-skills.html · 亮色主题，销售技能树和晋级路径
27


① Tailwind Config 色板配置
代码块
<script id="tailwind-config">
        tailwind.config = {
          darkMode: "class",
          theme: {
            extend: {
              "colors": {
                      "outline": "#747686",
                      "secondary": "#994700",
                      "on-error": "#ffffff",
                      "secondary-fixed-dim": "#ffb68b",
                      "parent-rational": "#10B981",
                      "primary-container": "#1e52d9",
                      "on-tertiary-fixed": "#002113",
                      "on-primary": "#ffffff",
                      "failure-red": "#EF4444",
                      "surface-variant": "#d8e3fb",
                      "on-primary-container": "#cfd7ff",
                      "on-error-container": "#93000a",
                      "on-background": "#111c2d",
                      "on-surface": "#111c2d",
                      "tertiary-fixed": "#6ffbbe",
                      "mascot-gold": "#FF9F1C",
                      "on-tertiary-fixed-variant": "#005236",
                      "error": "#ba1a1a",
                      "on-secondary-container": "#592600",
                      "surface-dim": "#cfdaf2",
                      "tertiary": "#005237",
                      "on-secondary": "#ffffff",
                      "surface-bg": "#F8FAFC",
                      "secondary-fixed": "#ffdbc8",
                      "tertiary-fixed-dim": "#4edea3",
                      "on-primary-fixed-variant": "#003ab1",
                      "parent-observing": "#718096",
                      "inverse-surface": "#263143",
                      "surface-bright": "#f9f9ff",
                      "surface-container": "#e7eeff",
                      "on-secondary-fixed": "#321200",
                      "surface-tint": "#1d52d9",
                      "on-tertiary": "#ffffff",
                      "inverse-on-surface": "#ecf1ff",
                      "surface-container-lowest": "#ffffff",
                      "parent-confused": "#00B2FF",
                      "tertiary-container": "#006d4a",
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
42
43


                      "surface-container-low": "#f0f3ff",
                      "surface": "#f9f9ff",
                      "inverse-primary": "#b6c4ff",
                      "background": "#f9f9ff",
                      "on-secondary-fixed-variant": "#753400",
                      "primary": "#003bb2",
                      "primary-fixed": "#dce1ff",
                      "on-surface-variant": "#434654",
                      "surface-container-highest": "#d8e3fb",
                      "on-primary-fixed": "#00164f",
                      "on-tertiary-container": "#65f2b5",
                      "secondary-container": "#fb7800",
                      "parent-anxious": "#FF7A00",
                      "surface-container-high": "#dee8ff",
                      "outline-variant": "#c4c5d7",
                      "primary-fixed-dim": "#b6c4ff",
                      "error-container": "#ffdad6"
              },
              "borderRadius": {
                      "DEFAULT": "0.25rem",
                      "lg": "1rem",
                      "xl": "1.5rem",
                      "full": "9999px"
              },
              "spacing": {
                      "card-padding": "16px",
                      "unit": "8px",
                      "stack-sm": "8px",
                      "container-margin": "24px",
                      "stack-md": "16px",
                      "gutter": "16px"
              }
            }
          }
        }
      </script>
② Custom CSS 样式
代码块

        body { font-family: 'Inter', sans-serif; }
        .font-headline { font-family: 'Hanken Grotesk', sans-serif; }
        .skill-card-hover { transition: transform 0.2s cubic-bezier(0.34, 
1.56, 0.64, 1); }
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
1
2
3
4


        .skill-card-hover:hover { transform: translateY(-4px) scale(1.02); }
        .glass-effect { background: rgba(255, 255, 255, 0.05); backdrop-
filter: blur(12px); border: 1px solid rgba(255, 255, 255, 0.1); }
        .timeline-path-active { background: linear-gradient(90deg, #FF9F1C 0%, 
#FF9F1C 100%); }
        .timeline-path-dotted { background-image: radial-gradient(circle, 
#747686 2px, transparent 2px); background-size: 10px 10px; background-repeat: 
repeat-x; background-position: center; }

        /* Custom scrollbar for horizontal containers */
        .hide-scrollbar::-webkit-scrollbar { display: none; }
        .hide-scrollbar { -ms-overflow-style: none; scrollbar-width: none; }

③ Skills Body 技能库主体
代码块
</nav>
<div class="pt-6 border-t border-on-secondary-container/10 flex flex-col gap-4 
w-full px-2">
<a class="flex flex-col items-center gap-1 p-2 text-on-secondary-container/60 
hover:text-on-secondary-container hover:bg-secondary-fixed-dim/20 transition-
all duration-200 rounded-lg" href="#" title="设置">
<span class="material-symbols-outlined">settings</span>
<span class="text-[10px] font-bold">设置</span>
</a>
<a class="flex flex-col items-center gap-1 p-2 text-on-secondary-container/60 
hover:text-on-secondary-container hover:bg-secondary-fixed-dim/20 transition-
all duration-200 rounded-lg" href="#" title="帮助中心">
<span class="material-symbols-outlined">help</span>
<span class="text-[10px] font-bold">帮助</span>
</a>
</div>
</aside>
<!-- Top App Bar -->
<header class="flex justify-between items-center ml-20 px-container-margin h-
16 bg-on-primary-fixed border-b border-outline-variant z-40 sticky top-0">
<h1 class="font-headline-md text-headline-md font-black text-primary-
fixed">Squirrel AI Sales Platform</h1>
<div class="flex items-center gap-6">
<div class="relative hidden md:block">
<span class="material-symbols-outlined absolute left-3 top-1/2 -translate-y-
1/2 text-primary-fixed/60">search</span>
<input class="bg-white/5 border border-white/10 rounded-full py-1.5 pl-10 pr-4 
text-white text-sm focus:outline-none focus:ring-2 focus:ring-primary-fixed/30 
5
6
7
8
9
10
11
12
13
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


w-64" placeholder="搜索技能、话术..." type="text">
</div>
<div class="flex items-center gap-4 text-primary-fixed">
<div class="relative cursor-pointer hover:text-white transition-colors">
<span class="material-symbols-outlined">notifications</span>
<span class="absolute top-0 right-0 w-2 h-2 bg-failure-red rounded-full">
</span>
</div>
<div class="flex items-center gap-2 cursor-pointer group">
<div class="w-8 h-8 rounded-full border-2 border-primary-fixed overflow-
hidden">
<img alt="User Avatar" class="w-full h-full object-cover" 
src="https://lh3.googleusercontent.com/aida-
public/AB6AXuDyC3540DDjpUaOtaD57T5jNYmAL9IqVKHSbLwVkODswAn2YzcIFaTyneUyaCbgwkBQ
uvSPXrQijJUaVvhzO6h6iA5FXxwBNqVdiX07ZyCypqnmuEyn0tRlighfwJ0GABO0Ff8BUkGY2C0hrUA
ikuPd-
JZqaCMd3fSAucCQ2gwxdYsmA7YqdH_ln_H4xJGlsUWi0wlggIZKtwvxsh7ZkhA5JWTc5NlLw849c_0U
c79njJn4FXrwn7XQVcrXXLML9Z7aSOkvglMTvhhp">
</div>
<span class="text-sm font-bold group-hover:text-white transition-colors">销售精
英</span>
</div>
</div>
</div>
</header>
<!-- Main Content Area -->
<main class="ml-20 p-container-margin">
<!-- Hero Header with Master Liu Tip -->
<div class="mb-10 flex flex-col md:flex-row justify-between items-start 
md:items-end gap-6">
<div>
<h2 class="font-headline-lg text-headline-lg text-white mb-2">销冠技能库</h2>
<p class="font-body-lg text-body-lg text-primary-fixed/70">原子化话术模块与销售全
链路成长路径</p>
</div>
<!-- Master Liu Floating Prompt -->
<div class="flex items-center gap-4 bg-surface-container/10 p-4 rounded-xl 
border border-white/20 glass-effect max-w-md">
<div class="relative w-14 h-14 flex-shrink-0">
<img alt="Master Liu" class="rounded-full bg-mascot-gold p-1 shadow-lg border-
2 border-white/30" src="https://lh3.googleusercontent.com/aida-
public/AB6AXuDyC3540DDjpUaOtaD57T5jNYmAL9IqVKHSbLwVkODswAn2YzcIFaTyneUyaCbgwkBQ
uvSPXrQijJUaVvhzO6h6iA5FXxwBNqVdiX07ZyCypqnmuEyn0tRlighfwJ0GABO0Ff8BUkGY2C0hrUA
ikuPd-
JZqaCMd3fSAucCQ2gwxdYsmA7YqdH_ln_H4xJGlsUWi0wlggIZKtwvxsh7ZkhA5JWTc5NlLw849c_0U
c79njJn4FXrwn7XQVcrXXLML9Z7aSOkvglMTvhhp">
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


<div class="absolute -top-1 -right-1 w-5 h-5 bg-green-500 rounded-full border-
4 border-on-primary-fixed animate-pulse"></div>
</div>
<div>
<p class="text-xs font-bold text-mascot-gold mb-1">松鼠刘总 (Master Liu) 的建议：
</p>
<p class="text-body-base font-body-base text-white/90 italic leading-snug">
                    “今日重点攻克‘价格异议’。记住，不要先降价，要先涨价值感。你的掌握度
已到 85%，加油！”
                </p>
</div>
</div>
</div>
<!-- Main Tabs -->
<div class="flex flex-wrap gap-4 mb-8">
<button class="px-8 py-2.5 rounded-full bg-primary-container text-white font-
bold shadow-lg shadow-primary-container/30 border border-white/10">全部技能
</button>
<button class="px-8 py-2.5 rounded-full bg-white/5 text-primary-fixed border 
border-white/10 hover:bg-white/10 transition-colors font-bold">原子单卡</button>
<button class="px-8 py-2.5 rounded-full bg-white/5 text-primary-fixed border 
border-white/10 hover:bg-white/10 transition-colors font-bold">战术组卡</button>
<button class="px-8 py-2.5 rounded-full bg-white/5 text-primary-fixed border 
border-white/10 hover:bg-white/10 transition-colors font-bold">全链套卡</button>
</div>
<!-- Section 1: Single Skill Cards -->
<section class="mb-16">
<div class="flex items-center justify-between mb-8">
<div class="flex items-center gap-3">
<span class="material-symbols-outlined text-mascot-gold text-3xl" style="font-
variation-settings: 'FILL' 1;">star</span>
<h3 class="font-headline-md text-headline-md text-white">原子单卡 (Single 
Skills)</h3>
</div>
<a class="text-primary-fixed/60 hover:text-white text-sm font-bold flex items-
center gap-1" href="#">查看全部 <span class="material-symbols-outlined text-
sm">arrow_forward</span></a>
</div>
<div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
<!-- Skill Card 1: Mastered -->
<div class="bg-white rounded-2xl p-5 flex flex-col skill-card-hover cursor-
pointer border-b-[6px] border-parent-rational shadow-xl relative group">
<div class="absolute top-4 right-4 flex items-center gap-1.5">
<span class="text-[10px] font-black px-2 py-0.5 rounded bg-parent-rational/10 
text-parent-rational border border-parent-rational/20">LV.1 基础</span>
</div>
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


<div class="w-12 h-12 bg-parent-rational/10 rounded-xl flex items-center 
justify-center text-parent-rational mb-4">
<span class="material-symbols-outlined text-3xl" style="font-variation-
settings: 'FILL' 1;">check_circle</span>
</div>
<h4 class="font-headline-md text-headline-md text-on-surface mb-1">SK-01 焦虑安
抚</h4>
<p class="text-xs font-semibold text-outline mb-4">核心：同理心共鸣与情绪降温</p>
<div class="mt-auto">
<div class="flex justify-between items-center mb-1">
<span class="text-[10px] font-bold text-parent-rational">掌握度: 100% (已精通)
</span>
<span class="material-symbols-outlined text-parent-rational text-
xs">verified</span>
</div>
<div class="h-1.5 w-full bg-surface-container-low rounded-full overflow-
hidden">
<div class="h-full bg-parent-rational w-full"></div>
</div>
</div>
<div class="mt-4 pt-4 border-t border-outline-variant/30">
<p class="text-[11px] leading-relaxed italic text-on-surface-variant group-
hover:text-on-surface transition-colors">
                        “先处理情绪，后处理问题。这套话术能显著降低客户防御心理。”
                    </p>
</div>
</div>
<!-- Skill Card 2: In Progress -->
<div class="bg-white rounded-2xl p-5 flex flex-col skill-card-hover cursor-
pointer border-b-[6px] border-mascot-gold shadow-xl relative group">
<div class="absolute top-4 right-4 flex items-center gap-1.5">
<span class="text-[10px] font-black px-2 py-0.5 rounded bg-mascot-gold/10 text-
secondary border border-mascot-gold/20">LV.2 进阶</span>
</div>
<div class="w-12 h-12 bg-mascot-gold/10 rounded-xl flex items-center justify-
center text-mascot-gold mb-4">
<span class="material-symbols-outlined text-3xl">payments</span>
</div>
<h4 class="font-headline-md text-headline-md text-on-surface mb-1">SK-05 价格异
议</h4>
<p class="text-xs font-semibold text-outline mb-4">核心：价值重塑与价格拆解</p>
<div class="mt-auto">
<div class="flex justify-between items-center mb-1">
<span class="text-[10px] font-bold text-mascot-gold">掌握度: 85% (对练中)</span>
</div>
<div class="h-1.5 w-full bg-surface-container-low rounded-full overflow-
hidden">
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
108
109
110
111
112
113


<div class="h-full bg-mascot-gold w-[85%] animate-pulse"></div>
</div>
</div>
<div class="mt-4 pt-4 border-t border-outline-variant/30">
<p class="text-[11px] leading-relaxed italic text-on-surface-variant">
                        “不要直接打折，要通过拆解服务颗粒度，让客户觉得占了便宜。”
                    </p>
</div>
</div>
<!-- Skill Card 3: In Progress -->
<div class="bg-white rounded-2xl p-5 flex flex-col skill-card-hover cursor-
pointer border-b-[6px] border-mascot-gold shadow-xl relative group">
<div class="absolute top-4 right-4 flex items-center gap-1.5">
<span class="text-[10px] font-black px-2 py-0.5 rounded bg-mascot-gold/10 text-
secondary border border-mascot-gold/20">LV.2 进阶</span>
</div>
<div class="w-12 h-12 bg-mascot-gold/10 rounded-xl flex items-center justify-
center text-mascot-gold mb-4">
<span class="material-symbols-outlined text-3xl">verified_user</span>
</div>
<h4 class="font-headline-md text-headline-md text-on-surface mb-1">SK-06 效果质
疑</h4>
<p class="text-xs font-semibold text-outline mb-4">核心：数据背书与对标证明</p>
<div class="mt-auto">
<div class="flex justify-between items-center mb-1">
<span class="text-[10px] font-bold text-mascot-gold">掌握度: 42%</span>
</div>
<div class="h-1.5 w-full bg-surface-container-low rounded-full overflow-
hidden">
<div class="h-full bg-mascot-gold w-[42%]"></div>
</div>
</div>
<div class="mt-4 pt-4 border-t border-outline-variant/30">
<p class="text-[11px] leading-relaxed italic text-on-surface-variant">
                        “针对同行对标数据，建立绝对权威感。此环节切忌神色心虚。”
                    </p>
</div>
</div>
<!-- Skill Card 4: Locked/New -->
<div class="bg-white rounded-2xl p-5 flex flex-col skill-card-hover cursor-
pointer border-b-[6px] border-primary shadow-xl relative group">
<div class="absolute top-4 right-4 flex items-center gap-1.5">
<span class="text-[10px] font-black px-2 py-0.5 rounded bg-primary/10 text-
primary border border-primary/20">LV.3 高级</span>
</div>
<div class="w-12 h-12 bg-primary/10 rounded-xl flex items-center justify-
center text-primary mb-4">
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
149
150
151
152


<span class="material-symbols-outlined text-3xl">staircase</span>
</div>
<h4 class="font-headline-md text-headline-md text-on-surface mb-1">SK-08 缔结临
门</h4>
<p class="text-xs font-semibold text-outline mb-4">核心：场景假设与二选一成交</p>
<div class="mt-auto">
<div class="flex justify-between items-center mb-1">
<span class="text-[10px] font-bold text-primary">掌握度: 12% (待突破)</span>
</div>
<div class="h-1.5 w-full bg-surface-container-low rounded-full overflow-
hidden">
<div class="h-full bg-primary w-[12%]"></div>
</div>
</div>
<div class="mt-4 pt-4 border-t border-outline-variant/30">
<p class="text-[11px] leading-relaxed italic text-on-surface-variant">
                        “最考验心态的一步，学会通过引导性提问让客户说出‘是’。”
                    </p>
</div>
</div>
</div>
</section>
<!-- Section 2: Skill Group Section (Rich Connections) -->
<section class="mb-16">
<div class="flex items-center gap-3 mb-8">
<span class="material-symbols-outlined text-parent-confused text-3xl" 
style="font-variation-settings: 'FILL' 1;">layers</span>
<h3 class="font-headline-md text-headline-md text-white">战术组卡 (Skill Groups)
</h3>
</div>
<div class="grid grid-cols-1 lg:grid-cols-2 gap-8">
<!-- Group Card 1: Advanced Flow -->
<div class="bg-white rounded-2xl p-8 border-l-[16px] border-parent-anxious 
shadow-2xl relative overflow-hidden group">
<div class="absolute top-0 right-0 p-3 bg-parent-anxious/10 rounded-bl-2xl">
<div class="flex flex-col items-end">
<span class="text-[10px] font-black text-parent-anxious">高难度战术</span>
<div class="flex gap-0.5 mt-1">
<span class="material-symbols-outlined text-[12px] text-parent-anxious" 
style="font-variation-settings: 'FILL' 1;">star</span>
<span class="material-symbols-outlined text-[12px] text-parent-anxious" 
style="font-variation-settings: 'FILL' 1;">star</span>
<span class="material-symbols-outlined text-[12px] text-parent-anxious" 
style="font-variation-settings: 'FILL' 1;">star</span>
</div>
</div>
</div>
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
173
174
175
176
177
178
179
180
181
182
183
184
185
186
187
188
189
190
191


<div class="flex justify-between items-start mb-10">
<div>
<h4 class="text-2xl font-black text-on-surface mb-2">拒绝处理全家桶</h4>
<div class="flex items-center gap-4 text-xs font-bold text-outline">
<span class="flex items-center gap-1"><span class="material-symbols-outlined 
text-sm">schedule</span> 15 分钟</span>
<span class="flex items-center gap-1 text-parent-rational"><span 
class="material-symbols-outlined text-sm">database</span> +500 XP</span>
</div>
</div>
<button class="bg-parent-anxious text-white px-6 py-3 rounded-xl font-bold 
hover:scale-105 active:scale-95 transition-all shadow-lg shadow-parent-
anxious/30">
                        开启挑战
                    </button>
</div>
<!-- Interactive Node Map visualization -->
<div class="relative flex items-center justify-between px-4">
<!-- Connector SVG -->
<svg class="absolute top-1/2 left-0 w-full h-10 -translate-y-1/2 pointer-
events-none overflow-visible" fill="none" preserveAspectRatio="none">
<path class="opacity-30" d="M 40,20 C 100,20 150,20 220,20" stroke="#FF7A00" 
stroke-dasharray="6 4" stroke-width="2"></path>
<path class="opacity-30" d="M 260,20 C 310,20 360,20 420,20" stroke="#FF7A00" 
stroke-dasharray="6 4" stroke-width="2"></path>
</svg>
<!-- Node 1 -->
<div class="z-10 flex flex-col items-center gap-2 group/node">
<div class="w-16 h-16 bg-white rounded-full shadow-lg border-4 border-parent-
anxious flex items-center justify-center text-parent-anxious font-black text-
xl group-hover/node:scale-110 transition-transform cursor-help" title="SK-05: 
价格策略">05</div>
<span class="text-[11px] font-black text-on-surface">价格异议</span>
</div>
<span class="material-symbols-outlined text-parent-anxious/40 animate-
pulse">keyboard_double_arrow_right</span>
<!-- Node 2 -->
<div class="z-10 flex flex-col items-center gap-2 group/node">
<div class="w-16 h-16 bg-white rounded-full shadow-lg border-4 border-parent-
anxious flex items-center justify-center text-parent-anxious font-black text-
xl group-hover/node:scale-110 transition-transform cursor-help" title="SK-06: 
信任建立">06</div>
<span class="text-[11px] font-black text-on-surface">效果质疑</span>
</div>
<span class="material-symbols-outlined text-parent-anxious/40 animate-
pulse">keyboard_double_arrow_right</span>
<!-- Node 3 -->
192
193
194
195
196
197
198
199
200
201
202
203
204
205
206
207
208
209
210
211
212
213
214
215
216
217
218
219
220
221
222
223


<div class="z-10 flex flex-col items-center gap-2 group/node">
<div class="w-16 h-16 bg-white rounded-full shadow-lg border-4 border-parent-
anxious flex items-center justify-center text-parent-anxious font-black text-
xl group-hover/node:scale-110 transition-transform cursor-help" title="SK-08: 
最后冲刺">08</div>
<span class="text-[11px] font-black text-on-surface">缔结引导</span>
</div>
</div>
<div class="mt-8 bg-surface-container-low p-4 rounded-xl border border-outline-
variant/20">
<p class="text-xs text-on-surface-variant flex gap-2">
<span class="material-symbols-outlined text-sm text-mascot-gold" style="font-
variation-settings: 'FILL' 1;">lightbulb</span>
<span>松鼠刘总：这个组合要求极高的灵活性，建议在‘焦虑安抚’满分后再尝试。</span>
</p>
</div>
</div>
<!-- Group Card 2: Starter Pack -->
<div class="bg-white rounded-2xl p-8 border-l-[16px] border-parent-rational 
shadow-2xl relative overflow-hidden group">
<div class="absolute top-0 right-0 p-3 bg-parent-rational/10 rounded-bl-2xl">
<div class="flex flex-col items-end">
<span class="text-[10px] font-black text-parent-rational">新手推荐</span>
<div class="flex gap-0.5 mt-1">
<span class="material-symbols-outlined text-[12px] text-parent-rational" 
style="font-variation-settings: 'FILL' 1;">star</span>
<span class="material-symbols-outlined text-[12px] text-parent-rational/30" 
style="font-variation-settings: 'FILL' 1;">star</span>
<span class="material-symbols-outlined text-[12px] text-parent-rational/30" 
style="font-variation-settings: 'FILL' 1;">star</span>
</div>
</div>
</div>
<div class="flex justify-between items-start mb-10">
<div>
<h4 class="text-2xl font-black text-on-surface mb-2">破冰升温组合技</h4>
<div class="flex items-center gap-4 text-xs font-bold text-outline">
<span class="flex items-center gap-1"><span class="material-symbols-outlined 
text-sm">schedule</span> 8 分钟</span>
<span class="flex items-center gap-1 text-parent-rational"><span 
class="material-symbols-outlined text-sm">database</span> +200 XP</span>
</div>
</div>
<button class="bg-parent-rational text-white px-6 py-3 rounded-xl font-bold 
hover:scale-105 active:scale-95 transition-all shadow-lg shadow-parent-
rational/30">
                        开启挑战
224
225
226
227
228
229
230
231
232
233
234
235
236
237
238
239
240
241
242
243
244
245
246
247
248
249
250
251
252
253
254
255
256
257


                    </button>
</div>
<!-- Node visualization -->
<div class="relative flex items-center justify-between px-4">
<div class="z-10 flex flex-col items-center gap-2 group/node">
<div class="w-16 h-16 bg-white rounded-full shadow-lg border-4 border-parent-
rational flex items-center justify-center text-parent-rational font-black text-
xl group-hover/node:scale-110 transition-transform">01</div>
<span class="text-[11px] font-black text-on-surface">焦虑安抚</span>
</div>
<span class="material-symbols-outlined text-parent-rational/40 animate-
pulse">arrow_forward</span>
<div class="z-10 flex flex-col items-center gap-2 group/node">
<div class="w-16 h-16 bg-white rounded-full shadow-lg border-4 border-parent-
rational flex items-center justify-center text-parent-rational font-black text-
xl group-hover/node:scale-110 transition-transform">02</div>
<span class="text-[11px] font-black text-on-surface">信任破冰</span>
</div>
<span class="material-symbols-outlined text-parent-rational/40 animate-
pulse">arrow_forward</span>
<div class="z-10 flex flex-col items-center gap-2 group/node">
<div class="w-16 h-16 bg-white rounded-full shadow-lg border-4 border-parent-
rational flex items-center justify-center text-parent-rational font-black text-
xl group-hover/node:scale-110 transition-transform">03</div>
<span class="text-[11px] font-black text-on-surface">精准提问</span>
</div>
</div>
<div class="mt-8 bg-surface-container-low p-4 rounded-xl border border-outline-
variant/20">
<p class="text-xs text-on-surface-variant flex gap-2">
<span class="material-symbols-outlined text-sm text-mascot-gold" style="font-
variation-settings: 'FILL' 1;">lightbulb</span>
<span>松鼠刘总：这是入职必练的基本功，平均练习 5 次即可掌握其精髓。</span>
</p>
</div>
</div>
</div>
</section>
<!-- Section 3: Skill Chain (Roadmap Roadmap) -->
<section class="mb-20">
<div class="flex items-center gap-3 mb-8">
<span class="material-symbols-outlined text-tertiary-fixed text-3xl" 
style="font-variation-settings: 'FILL' 1;">account_tree</span>
<h3 class="font-headline-md text-headline-md text-white">全链通关地图 (Skill 
Chain Roadmap)</h3>
</div>
258
259
260
261
262
263
264
265
266
267
268
269
270
271
272
273
274
275
276
277
278
279
280
281
282
283
284
285
286
287
288
289
290
291


<div class="bg-primary-container/20 rounded-[2.5rem] p-10 border border-
white/10 relative overflow-hidden">
<!-- Dynamic BG effects -->
<div class="absolute -right-40 -top-40 w-96 h-96 bg-primary-container/30 
rounded-full blur-[100px]"></div>
<div class="absolute -left-40 -bottom-40 w-96 h-96 bg-mascot-gold/10 rounded-
full blur-[100px]"></div>
<div class="relative z-10">
<div class="mb-12">
<h4 class="text-3xl font-black text-white mb-2">签约临门一脚：全链路大满贯</h4>
<p class="text-primary-fixed/60 max-w-2xl">这不仅是一个练测，这是一场模拟真实销售全
流程的战斗。从客户的第一句冷漠到最后扫码支付，你需要连贯应用所有已掌握的技能。</p>
</div>
<!-- Horizontal Roadmap -->
<div class="flex items-center gap-0 overflow-x-auto hide-scrollbar pb-16 pt-8 
px-4">
<!-- MileStone 1 -->
<div class="flex-shrink-0 flex flex-col items-center relative">
<div class="w-24 h-24 bg-white rounded-2xl flex flex-col items-center justify-
center shadow-2xl ring-4 ring-parent-rational relative group cursor-pointer 
hover:-translate-y-2 transition-transform">
<span class="text-2xl font-black text-on-surface">SK-01</span>
<span class="text-[10px] font-black text-parent-rational">已掌握</span>
<div class="absolute -top-3 -right-3 w-8 h-8 bg-parent-rational rounded-full 
border-4 border-on-primary-fixed flex items-center justify-center">
<span class="material-symbols-outlined text-white text-sm" style="font-
variation-settings: 'FILL' 1;">check</span>
</div>
</div>
<div class="mt-6 text-center">
<p class="text-white font-bold text-sm">起点：情绪共鸣</p>
<p class="text-primary-fixed/40 text-[10px] font-bold">第一阶段：破除冰冷</p>
</div>
</div>
<!-- Connect Line -->
<div class="w-24 h-1 timeline-path-active mb-14 self-center opacity-60"></div>
<!-- MileStone 2 -->
<div class="flex-shrink-0 flex flex-col items-center relative">
<div class="w-24 h-24 bg-white rounded-2xl flex flex-col items-center justify-
center shadow-2xl ring-4 ring-mascot-gold relative group cursor-pointer hover:-
translate-y-2 transition-transform">
<span class="text-2xl font-black text-on-surface">SK-05</span>
<span class="text-[10px] font-black text-mascot-gold">熟练度 85%</span>
<div class="absolute -top-3 -right-3 w-8 h-8 bg-mascot-gold rounded-full 
border-4 border-on-primary-fixed flex items-center justify-center">
<span class="material-symbols-outlined text-white text-sm">trending_up</span>
</div>
292
293
294
295
296
297
298
299
300
301
302
303
304
305
306
307
308
309
310
311
312
313
314
315
316
317
318
319
320
321
322
323
324
325
326


</div>
<div class="mt-6 text-center">
<p class="text-white font-bold text-sm">中继：价值锚定</p>
<p class="text-primary-fixed/40 text-[10px] font-bold">第二阶段：建立锚点</p>
</div>
</div>
<!-- Connect Line -->
<div class="w-24 h-1 timeline-path-dotted mb-14 self-center"></div>
<!-- MileStone 3 -->
<div class="flex-shrink-0 flex flex-col items-center relative">
<div class="w-24 h-24 bg-white/10 rounded-2xl flex flex-col items-center 
justify-center shadow-2xl border-2 border-white/20 backdrop-blur-md relative 
group cursor-pointer hover:-translate-y-2 transition-transform opacity-60">
<span class="text-2xl font-black text-white/50">SK-11</span>
<span class="text-[10px] font-black text-white/30">待解锁</span>
<div class="absolute -top-3 -right-3 w-8 h-8 bg-outline rounded-full border-4 
border-on-primary-fixed flex items-center justify-center">
<span class="material-symbols-outlined text-white text-sm">lock</span>
</div>
</div>
<div class="mt-6 text-center">
<p class="text-white/40 font-bold text-sm">瓶颈：紧迫施压</p>
<p class="text-primary-fixed/20 text-[10px] font-bold">第三阶段：临门催化</p>
</div>
</div>
<!-- Connect Line -->
<div class="w-24 h-1 timeline-path-dotted mb-14 self-center"></div>
<!-- Final Challenge -->
<div class="flex-shrink-0 flex flex-col items-center relative">
<div class="w-32 h-32 bg-gradient-to-br from-mascot-gold to-secondary rounded-
[2rem] flex flex-col items-center justify-center shadow-
[0_0_50px_rgba(255,159,28,0.3)] ring-4 ring-white/30 relative group cursor-
pointer hover:scale-110 transition-transform">
<span class="material-symbols-outlined text-white text-4xl mb-
1">emoji_events</span>
<span class="text-[11px] font-black text-white">全链终测</span>
<div class="absolute -top-4 -right-4 bg-tertiary-fixed text-on-tertiary-fixed 
font-black text-[10px] px-3 py-1 rounded-full shadow-lg">
                                奖:+1000XP
                            </div>
</div>
<div class="mt-6 text-center">
<p class="text-mascot-gold font-black text-lg">终点：交付成交</p>
<p class="text-white/60 text-xs font-bold">通向销冠的最后战役</p>
</div>
</div>
</div>
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
352
353
354
355
356
357
358
359
360
361
362
363
364
365


(注：内容由 AI 生成，请谨慎参考）
<div class="flex justify-center md:justify-end mt-4">
<button class="bg-white text-primary font-black py-5 px-12 rounded-2xl text-xl 
shadow-2xl hover:bg-primary-fixed hover:scale-105 transition-all active:scale-
95 flex items-center gap-3">
<span class="material-symbols-outlined">rocket_launch</span>
                        开始全链终极挑战
                    </button>
</div>
</div>
</div>
</section>

366
367
368
369
370
371
372
373
374
375