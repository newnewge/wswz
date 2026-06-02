# 模块三：家长图鉴库（Parent Role Library）

> 来源: 飞书文档「前端代码-松鼠ai培训助手前端界面」
> 模块: 家长图鉴库 · Module 3/9

---

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


文件：role-library.html · 深色主题（parent-* 四色体系）
① Tailwind Config 色板配置
代码块
<script id="tailwind-config">
      tailwind.config = {
        darkMode: "class",
        theme: {
          extend: {
            "colors": {
                    "tertiary-fixed-dim": "#4edea3",
                    "outline-variant": "#c4c5d7",
                    "on-surface": "#111c2d",
                    "surface-bg": "#F8FAFC",
                    "parent-observing": "#718096",
                    "parent-confused": "#00B2FF",
                    "surface-variant": "#d8e3fb",
                    "surface-container-high": "#dee8ff",
                    "on-tertiary-fixed": "#002113",
                    "primary": "#003bb2",
                    "on-error-container": "#93000a",
                    "surface-tint": "#1d52d9",
                    "tertiary-container": "#006d4a",
                    "inverse-surface": "#263143",
                    "surface-container-low": "#f0f3ff",
                    "surface": "#f9f9ff",
                    "tertiary-fixed": "#6ffbbe",
                    "on-primary": "#ffffff",
                    "outline": "#747686",
                    "on-primary-fixed-variant": "#003ab1",
                    "secondary-fixed-dim": "#ffb68b",
                    "on-tertiary": "#ffffff",
                    "surface-container-lowest": "#ffffff",
                    "primary-container": "#1e52d9",
                    "parent-rational": "#10B981",
                    "tertiary": "#005237",
                    "primary-fixed-dim": "#b6c4ff",
                    "background": "#0b1120",
                    "surface-dim": "#1e293b",
                    "on-secondary-container": "#592600",
                    "secondary-fixed": "#ffdbc8",
                    "surface-container-highest": "#d8e3fb",
                    "primary-fixed": "#dce1ff",
                    "parent-anxious": "#FF7A00",
                    "secondary-container": "#fb7800",
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


                    "on-surface-variant": "#434654",
                    "on-tertiary-container": "#65f2b5",
                    "failure-red": "#EF4444",
                    "secondary": "#994700",
                    "on-secondary-fixed-variant": "#753400",
                    "on-secondary-fixed": "#321200",
                    "on-primary-container": "#cfd7ff",
                    "on-secondary": "#ffffff",
                    "mascot-gold": "#FF9F1C",
                    "on-tertiary-fixed-variant": "#005236",
                    "inverse-primary": "#b6c4ff",
                    "on-error": "#ffffff",
                    "on-background": "#ffffff",
                    "surface-container": "#1e293b",
                    "error-container": "#ffdad6",
                    "error": "#ba1a1a",
                    "on-primary-fixed": "#00164f",
                    "inverse-on-surface": "#ecf1ff",
                    "surface-bright": "#f9f9ff"
            },
            "borderRadius": {
                    "DEFAULT": "0.25rem",
                    "lg": "0.5rem",
                    "xl": "0.75rem",
                    "2xl": "1.5rem",
                    "3xl": "2rem",
                    "full": "9999px"
            },
            "spacing": {
                    "stack-md": "16px",
                    "card-padding": "16px",
                    "gutter": "16px",
                    "stack-sm": "8px",
                    "container-margin": "24px",
                    "unit": "8px"
            },
            "fontFamily": {
                    "headline-lg-mobile": ["Hanken Grotesk"],
                    "body-lg": ["Inter"],
                    "label-caps": ["Inter"],
                    "headline-md": ["Hanken Grotesk"],
                    "headline-lg": ["Hanken Grotesk"],
                    "body-base": ["Inter"],
                    "annotation-italic": ["Inter"]
            },
            "fontSize": {
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
86
87


                    "headline-lg-mobile": ["24px", {"lineHeight": "32px", 
"fontWeight": "700"}],
                    "body-lg": ["16px", {"lineHeight": "24px", "fontWeight": 
"400"}],
                    "label-caps": ["12px", {"lineHeight": "16px", 
"letterSpacing": "0.05em", "fontWeight": "600"}],
                    "headline-md": ["20px", {"lineHeight": "28px", 
"fontWeight": "600"}],
                    "headline-lg": ["32px", {"lineHeight": "40px", 
"fontWeight": "700"}],
                    "body-base": ["14px", {"lineHeight": "22px", "fontWeight": 
"400"}],
                    "annotation-italic": ["12px", {"lineHeight": "16px", 
"fontWeight": "400"}]
            }
          },
        }
      }
    </script>
② Custom CSS 样式
代码块

        body {
            background-color: #0b1120;
            color: #ffffff;
            -webkit-font-smoothing: antialiased;
        }

        .persona-card {
            perspective: 1000px;
            height: 480px;
        }

        .persona-card-inner {
            position: relative;
            width: 100%;
            height: 100%;
            transition: transform 0.6s cubic-bezier(0.4, 0, 0.2, 1);
            transform-style: preserve-3d;
            cursor: pointer;
        }

        .persona-card:hover .persona-card-inner {
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


            transform: translateY(-8px);
        }

        .persona-card.flipped .persona-card-inner {
            transform: rotateY(180deg);
        }

        .card-front, .card-back {
            position: absolute;
            width: 100%;
            height: 100%;
            -webkit-backface-visibility: hidden;
            backface-visibility: hidden;
            border-radius: 2rem;
            display: flex;
            flex-direction: column;
            border-bottom-width: 8px;
        }

        .card-back {
            transform: rotateY(180deg);
        }

        .gamified-button {
            border-bottom-width: 4px;
            transition: all 0.1s ease-in-out;
        }
        .gamified-button:active {
            transform: translateY(2px);
            border-bottom-width: 2px;
        }

        ::-webkit-scrollbar {
            width: 8px;
        }
        ::-webkit-scrollbar-track {
            background: transparent;
        }
        ::-webkit-scrollbar-thumb {
            background: #1e293b;
            border-radius: 4px;
        }

③ Navigation 侧边导航栏
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


代码块
<nav class="h-full w-64 fixed left-0 top-0 overflow-y-auto bg-parent-anxious 
flex flex-col p-6 shrink-0 shadow-xl z-50">
<div class="flex items-center gap-3 mb-10">
<div class="w-12 h-12 rounded-full bg-white flex items-center justify-center 
overflow-hidden border-2 border-white shadow-lg">
<img alt="Squirrel AI Mascot" class="w-full h-full object-cover" 
src="https://lh3.googleusercontent.com/aida-
public/AB6AXuDkFSESY6yGGGN7rKl97ARxZjz6avS49KtS1Ki3V3pB-BXKQRV-
1BwNoe1Ko0NRnZEhKYQVUi-
JYFnsJxgqbcaAw0D3_JstNiwo4CBCnTKYLtHp8r3tDYdhs0psB0xM6HnNfmy4rOZAz7VgwfZdXR3_5u
riTcTvEBot9QN3MQtyXa5DX8Dcbq5lGlgLPUYCGk8uIAUQSeUT7gUC6KReIoxnG8BsCLbePCJT2wKoy
l0-Qm52KX27z7VwlF5TQjLp3_GM_xfkAQrRVNY7"/>
</div>
<div>
<h2 class="font-headline-md text-headline-md font-black text-white leading-
tight">Master Liu</h2>
<p class="font-label-caps text-[10px] text-white/70 uppercase tracking-
widest">AI Sales Mentor</p>
</div>
</div>
<div class="flex-1 space-y-3">
<a class="flex items-center gap-4 p-4 rounded-2xl text-white/90 hover:bg-
white/20 transition-all duration-200" href="#">
<span class="material-symbols-outlined text-[24px]" style="font-variation-
settings: 'FILL' 1;">menu_book</span>
<span class="font-body-base text-body-base font-bold">场景库</span>
</a>
<a class="flex items-center gap-4 p-4 rounded-2xl bg-white text-parent-anxious 
font-bold shadow-lg border-b-4 border-orange-700/20" href="#">
<span class="material-symbols-outlined text-[24px]" style="font-variation-
settings: 'FILL' 1;">person_search</span>
<span class="font-body-base text-body-base">角色库</span>
</a>
<a class="flex items-center gap-4 p-4 rounded-2xl text-white/90 hover:bg-
white/20 transition-all duration-200" href="#">
<span class="material-symbols-outlined text-[24px]" style="font-variation-
settings: 'FILL' 1;">history</span>
<span class="font-body-base text-body-base font-bold">培训历史</span>
</a>
<a class="flex items-center gap-4 p-4 rounded-2xl text-white/90 hover:bg-
white/20 transition-all duration-200" href="#">
<span class="material-symbols-outlined text-[24px]" style="font-variation-
settings: 'FILL' 1;">dashboard</span>
<span class="font-body-base text-body-base font-bold">团队看板</span>
</a>
</div>
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


<button class="gamified-button mt-10 w-full py-4 bg-white text-parent-anxious 
border-orange-700/20 rounded-2xl font-headline-md text-headline-md text-[18px] 
font-black shadow-lg">开始新对练</button>
<div class="mt-auto space-y-2 border-t border-white/20 pt-6">
<a class="flex items-center gap-3 p-2 rounded-xl text-white/70 hover:bg-
white/10 transition-colors" href="#">
<span class="material-symbols-outlined text-[20px]">settings</span>
<span class="font-label-caps text-label-caps">设置</span>
</a>
<a class="flex items-center gap-3 p-2 rounded-xl text-white/70 hover:bg-
white/10 transition-colors" href="#">
<span class="material-symbols-outlined text-[20px]">help</span>
<span class="font-label-caps text-label-caps">支持</span>
</a>
</div>
</nav>
④ Role Cards 家长角色卡组件
代码块
</nav>
<!-- Main Content -->
<main class="flex-1 ml-64 flex flex-col overflow-hidden bg-background">
<!-- Top Header -->
<header class="top-0 sticky z-40 bg-[#0f172a]/80 backdrop-blur-md flex justify-
between items-center w-full px-8 py-4 border-b border-white/5">
<h1 class="font-headline-lg text-2xl font-black text-white tracking-tight flex 
items-center gap-2">
<span class="w-2 h-8 bg-mascot-gold rounded-full"></span>
                家长图鉴中心
            </h1>
<div class="flex items-center gap-4">
<button class="w-10 h-10 flex items-center justify-center rounded-2xl bg-
surface-dim hover:bg-surface-container transition-colors">
<span class="material-symbols-outlined text-white">notifications</span>
</button>
<div class="h-10 px-4 flex items-center gap-2 rounded-2xl bg-surface-dim 
border border-white/5">
<span class="material-symbols-outlined text-mascot-gold" style="font-variation-
settings: 'FILL' 1;">emoji_events</span>
<span class="font-bold text-white">12,450</span>
</div>
<button class="w-10 h-10 flex items-center justify-center rounded-2xl bg-
surface-dim hover:bg-surface-container transition-colors">
<span class="material-symbols-outlined text-white">account_circle</span>
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


</button>
</div>
</header>
<!-- Gallery Area -->
<div class="flex-1 overflow-y-auto p-8 custom-scrollbar">
<div class="max-w-[1400px] mx-auto">
<div class="mb-10 flex justify-between items-end">
<div>
<h2 class="font-headline-lg text-4xl font-black text-white mb-3">家长图鉴库</h2>
<p class="font-body-lg text-outline-variant max-w-xl">通过研究不同的家长人设，制定
差异化的沟通话术，提升转化率。点击卡片查看详细攻略。</p>
</div>
<div class="flex p-1 bg-surface-dim rounded-2xl border border-white/5">
<button class="px-6 py-2 rounded-xl bg-primary text-white font-bold text-sm 
transition-all">全部类型</button>
<button class="px-6 py-2 rounded-xl text-outline-variant hover:text-white font-
bold text-sm transition-all">高潜力型</button>
<button class="px-6 py-2 rounded-xl text-outline-variant hover:text-white font-
bold text-sm transition-all">待开发型</button>
</div>
</div>
<!-- Two-Row Grid Layout -->
<div class="grid grid-cols-1 md:grid-cols-2 xl:grid-cols-4 gap-8">
<!-- Card 1: P-01 张宝妈 -->
<div class="persona-card" onclick="this.classList.toggle('flipped')">
<div class="persona-card-inner">
<div class="card-front bg-surface-dim border-parent-anxious/30 border-b-parent-
anxious p-6">
<div class="flex justify-between items-start mb-4">
<span class="px-3 py-1 rounded-lg bg-parent-anxious/20 text-parent-anxious 
font-bold text-[10px] tracking-widest border border-parent-anxious/30">P-
01</span>
<span class="material-symbols-outlined text-white/20">info</span>
</div>
<div class="w-full h-48 bg-background/50 rounded-2xl mb-6 flex items-center 
justify-center overflow-hidden border border-white/5">
<img alt="张宝妈" class="h-40 w-40 object-contain drop-shadow-2xl hover:scale-
110 transition-transform duration-500" 
src="https://lh3.googleusercontent.com/aida/ADBb0ujtodUvUVt7GCpiBPHexAlVMsXVh2_
BzsMy6fzL0dzijwzvFROCdl5orj-kQYAQhr_U34cFVtZjce3AbJfoqJh5NnIxA3d1MRrme-
6x3Re_PJkDQ0zmaf0M9nLuF9t-4wTiTYOsw2K7HRgAtGkvjuYiq0DxxsoqKNfNa7y-dc-
C1VMwdZCbp9uMz6nI-_f3pp-6QuGdcuqTgHzqXS0ACU4QDy_-
VI7IlKgYmQhT30vaqNhjUPYa7l3zgrs"/>
</div>
<div class="text-center">
<h3 class="text-2xl font-black text-white mb-1">张宝妈</h3>
<div class="flex items-center justify-center gap-2 mb-4">
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


<span class="w-2 h-2 rounded-full bg-parent-anxious animate-pulse"></span>
<p class="text-parent-anxious font-bold text-sm tracking-widest uppercase">焦虑
型</p>
</div>
<div class="bg-background/80 rounded-2xl p-4 border border-white/5 relative">
<span class="material-symbols-outlined absolute -top-3 left-4 text-parent-
anxious bg-background rounded-full p-1 text-[16px]">format_quote</span>
<p class="text-sm text-outline-variant italic leading-relaxed">“我担心孩子跟不上
进度，你们能保证效果吗？”</p>
</div>
</div>
</div>
<div class="card-back bg-[#1e1e2d] border-parent-anxious border-b-parent-
anxious p-6 overflow-y-auto">
<h4 class="text-parent-anxious font-black mb-4 flex items-center gap-2">
<span class="material-symbols-outlined text-[20px]">psychology</span> 核心需求
                                </h4>
<ul class="space-y-2 mb-6">
<li class="flex items-start gap-2 text-[13px] text-white/80">
<span class="material-symbols-outlined text-parent-anxious text-[16px] mt-
0.5">check_circle</span>
                                        需要即时可见的学习反馈
                                    </li>
<li class="flex items-start gap-2 text-[13px] text-white/80">
<span class="material-symbols-outlined text-parent-anxious text-[16px] mt-
0.5">check_circle</span>
                                        渴望专业的承诺与心理安抚
                                    </li>
</ul>
<h4 class="text-parent-anxious font-black mb-4 flex items-center gap-2">
<span class="material-symbols-outlined text-[20px]">error</span> 沟通难点
                                </h4>
<p class="text-[13px] text-white/80 mb-6 bg-black/20 p-3 rounded-xl border 
border-white/5">对机构信任度波动大，容易被竞争对手的话术干扰。</p>
<div class="mt-auto pt-4 border-t border-white/10">
<p class="text-[10px] text-white/40 uppercase mb-2">推荐匹配销售</p>
<div class="flex items-center gap-3">
<div class="w-8 h-8 rounded-full bg-parent-anxious"></div>
<span class="text-sm font-bold text-white">耐受型专家级销售</span>
</div>
</div>
</div>
</div>
</div>
<!-- Card 2: P-02 王宝爸 -->
<div class="persona-card" onclick="this.classList.toggle('flipped')">
<div class="persona-card-inner">
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
86
87
88
89
90
91
92


<div class="card-front bg-surface-dim border-parent-confused/30 border-b-
parent-confused p-6">
<div class="flex justify-between items-start mb-4">
<span class="px-3 py-1 rounded-lg bg-parent-confused/20 text-parent-confused 
font-bold text-[10px] tracking-widest border border-parent-confused/30">P-
02</span>
<span class="material-symbols-outlined text-white/20">info</span>
</div>
<div class="w-full h-48 bg-background/50 rounded-2xl mb-6 flex items-center 
justify-center overflow-hidden border border-white/5">
<img alt="王宝爸" class="h-40 w-40 object-contain drop-shadow-2xl hover:scale-
110 transition-transform duration-500" 
src="https://lh3.googleusercontent.com/aida/ADBb0uj4Dw06TxBvUxvOeXR50kTaTaEpo-
nqRKL9YTzEZHk0CrPNqHkFiDVDr4GFhvNRohci4Wn6mvJ00G8kHfYlDvjZFqpnUsQY33okMC7wkAMBm
kbmAbz5Ix8dNK7RlA06EPXFRa8Y9wApNhLbo3nGmLoxTnAZIYM9QFeQVNYUqoyfmfdU-5-
Y3f4NSfAu99y5sIS8eOxH3Kgwldr3Ox4dwhLRCa15zWvwm5RukvefcwiR0ZgzgshIMZQ3Ip1-"/>
</div>
<div class="text-center">
<h3 class="text-2xl font-black text-white mb-1">王宝爸</h3>
<div class="flex items-center justify-center gap-2 mb-4">
<span class="w-2 h-2 rounded-full bg-parent-confused animate-pulse"></span>
<p class="text-parent-confused font-bold text-sm tracking-widest uppercase">迷茫
型</p>
</div>
<div class="bg-background/80 rounded-2xl p-4 border border-white/5 relative">
<span class="material-symbols-outlined absolute -top-3 left-4 text-parent-
confused bg-background rounded-full p-1 text-[16px]">format_quote</span>
<p class="text-sm text-outline-variant italic leading-relaxed">“机构太多了，我真
不知道该选哪一个比较好。”</p>
</div>
</div>
</div>
<div class="card-back bg-[#1e1e2d] border-parent-confused border-b-parent-
confused p-6 overflow-y-auto">
<h4 class="text-parent-confused font-black mb-4 flex items-center gap-2">
<span class="material-symbols-outlined text-[20px]">psychology</span> 核心需求
                                </h4>
<ul class="space-y-2 mb-6">
<li class="flex items-start gap-2 text-[13px] text-white/80">
<span class="material-symbols-outlined text-parent-confused text-[16px] mt-
0.5">check_circle</span>
                                        需要权威的规划与对比建议
                                    </li>
<li class="flex items-start gap-2 text-[13px] text-white/80">
<span class="material-symbols-outlined text-parent-confused text-[16px] mt-
0.5">check_circle</span>
                                        简化决策流程，降低选择难度
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


                                    </li>
</ul>
<h4 class="text-parent-confused font-black mb-4 flex items-center gap-2">
<span class="material-symbols-outlined text-[20px]">error</span> 沟通难点
                                </h4>
<p class="text-[13px] text-white/80 mb-6 bg-black/20 p-3 rounded-xl border 
border-white/5">决策犹豫不决，需要销售具备极强的引导能力。</p>
<div class="mt-auto pt-4 border-t border-white/10">
<p class="text-[10px] text-white/40 uppercase mb-2">推荐匹配销售</p>
<div class="flex items-center gap-3">
<div class="w-8 h-8 rounded-full bg-parent-confused"></div>
<span class="text-sm font-bold text-white">强势引导型金牌销售</span>
</div>
</div>
</div>
</div>
</div>
<!-- Card 3: P-03 李宝爸 -->
<div class="persona-card" onclick="this.classList.toggle('flipped')">
<div class="persona-card-inner">
<div class="card-front bg-surface-dim border-parent-rational/30 border-b-
parent-rational p-6">
<div class="flex justify-between items-start mb-4">
<span class="px-3 py-1 rounded-lg bg-parent-rational/20 text-parent-rational 
font-bold text-[10px] tracking-widest border border-parent-rational/30">P-
03</span>
<span class="material-symbols-outlined text-white/20">info</span>
</div>
<div class="w-full h-48 bg-background/50 rounded-2xl mb-6 flex items-center 
justify-center overflow-hidden border border-white/5">
<img alt="李宝爸" class="h-40 w-40 object-contain drop-shadow-2xl hover:scale-
110 transition-transform duration-500" 
src="https://lh3.googleusercontent.com/aida/ADBb0uiuDNAXPsqNLuBn-98OREDzUBwLvK-
OEI9vHGSFkg4PIf_f9hKKtkD6Aj13pDsHfY3DTjtLDUN5sw1ae1PEM4GZCbW-
ngSBJabasxkAJ8CvikIKvsA4C8qGQhxZV_vSOkH75BYgtqkmcVdO_WSx_l5qAEhYjsOCtA8s3hrgGLJ
VcZR8imT8T11XSfeVv0XqlRaPQ2GxkmnzVxa91AQzQJi0eXYbhuJl3uzAVZLwq-qxDsOi6mvGx-
wgKSE"/>
</div>
<div class="text-center">
<h3 class="text-2xl font-black text-white mb-1">李宝爸</h3>
<div class="flex items-center justify-center gap-2 mb-4">
<span class="w-2 h-2 rounded-full bg-parent-rational animate-pulse"></span>
<p class="text-parent-rational font-bold text-sm tracking-widest uppercase">理性
型</p>
</div>
<div class="bg-background/80 rounded-2xl p-4 border border-white/5 relative">
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
153
154
155
156
157
158


<span class="material-symbols-outlined absolute -top-3 left-4 text-parent-
rational bg-background rounded-full p-1 text-[16px]">format_quote</span>
<p class="text-sm text-outline-variant italic leading-relaxed">“给我看具体的数
据，对比一下投资回报率。”</p>
</div>
</div>
</div>
<div class="card-back bg-[#1e1e2d] border-parent-rational border-b-parent-
rational p-6 overflow-y-auto">
<h4 class="text-parent-rational font-black mb-4 flex items-center gap-2">
<span class="material-symbols-outlined text-[20px]">psychology</span> 核心需求
                                </h4>
<ul class="space-y-2 mb-6">
<li class="flex items-start gap-2 text-[13px] text-white/80">
<span class="material-symbols-outlined text-parent-rational text-[16px] mt-
0.5">check_circle</span>
                                        数据驱动的证据与案例研究
                                    </li>
<li class="flex items-start gap-2 text-[13px] text-white/80">
<span class="material-symbols-outlined text-parent-rational text-[16px] mt-
0.5">check_circle</span>
                                        明确的产品差异点与技术优势
                                    </li>
</ul>
<h4 class="text-parent-rational font-black mb-4 flex items-center gap-2">
<span class="material-symbols-outlined text-[20px]">error</span> 沟通难点
                                </h4>
<p class="text-[13px] text-white/80 mb-6 bg-black/20 p-3 rounded-xl border 
border-white/5">对销售话术敏感，讨厌过度的情感化营销或虚假承诺。</p>
<div class="mt-auto pt-4 border-t border-white/10">
<p class="text-[10px] text-white/40 uppercase mb-2">推荐匹配销售</p>
<div class="flex items-center gap-3">
<div class="w-8 h-8 rounded-full bg-parent-rational"></div>
<span class="text-sm font-bold text-white">技术驱动型学术销售</span>
</div>
</div>
</div>
</div>
</div>
<!-- Card 4: P-04 赵宝妈 -->
<div class="persona-card" onclick="this.classList.toggle('flipped')">
<div class="persona-card-inner">
<div class="card-front bg-surface-dim border-parent-observing/30 border-b-
parent-observing p-6">
<div class="flex justify-between items-start mb-4">
<span class="px-3 py-1 rounded-lg bg-parent-observing/20 text-parent-observing 
font-bold text-[10px] tracking-widest border border-parent-observing/30">P-
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
192
193
194
195
196
197


04</span>
<span class="material-symbols-outlined text-white/20">info</span>
</div>
<div class="w-full h-48 bg-background/50 rounded-2xl mb-6 flex items-center 
justify-center overflow-hidden border border-white/5">
<img alt="赵宝妈" class="h-40 w-40 object-contain drop-shadow-2xl hover:scale-
110 transition-transform duration-500" 
src="https://lh3.googleusercontent.com/aida/ADBb0ujCvWt9r7lUeRlvZKdHM9zqpBkstG0
eB_aEgOUElblDrLakBOUQVwpeQeX__RIYCrhLBZN9TrDbPuWSRJAeut_p0gc72file-
Me3aa0JDLIuGrlDbmu_B12d0hrz5poyssgV0ekf1BbvREjPnH3_afqU1seHwtH5DzduZQ7jroZax4qx
pwYfVhAEsd6R6LZoIOhR6sqcMfzQTmOtvIqHmZAxOPhVVZzVNIjgfaUByXOTFm_GmYyvP241zQ"/>
</div>
<div class="text-center">
<h3 class="text-2xl font-black text-white mb-1">赵宝妈</h3>
<div class="flex items-center justify-center gap-2 mb-4">
<span class="w-2 h-2 rounded-full bg-parent-observing animate-pulse"></span>
<p class="text-parent-observing font-bold text-sm tracking-widest uppercase">观
望型</p>
</div>
<div class="bg-background/80 rounded-2xl p-4 border border-white/5 relative">
<span class="material-symbols-outlined absolute -top-3 left-4 text-parent-
observing bg-background rounded-full p-1 text-[16px]">format_quote</span>
<p class="text-sm text-outline-variant italic leading-relaxed">“我先看看别的家长
怎么说，暂时不急着订。”</p>
</div>
</div>
</div>
<div class="card-back bg-[#1e1e2d] border-parent-observing border-b-parent-
observing p-6 overflow-y-auto">
<h4 class="text-parent-observing font-black mb-4 flex items-center gap-2">
<span class="material-symbols-outlined text-[20px]">psychology</span> 核心需求
                                </h4>
<ul class="space-y-2 mb-6">
<li class="flex items-start gap-2 text-[13px] text-white/80">
<span class="material-symbols-outlined text-parent-observing text-[16px] mt-
0.5">check_circle</span>
                                        真实的家长口碑与社群背书
                                    </li>
<li class="flex items-start gap-2 text-[13px] text-white/80">
<span class="material-symbols-outlined text-parent-observing text-[16px] mt-
0.5">check_circle</span>
                                        低风险的试听或体验机会
                                    </li>
</ul>
<h4 class="text-parent-observing font-black mb-4 flex items-center gap-2">
<span class="material-symbols-outlined text-[20px]">error</span> 沟通难点
                                </h4>
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
224
225
226
227
228
229
230
231


<p class="text-[13px] text-white/80 mb-6 bg-black/20 p-3 rounded-xl border 
border-white/5">对主动销售有防备心理，需要慢节奏、温和的培育过程。</p>
<div class="mt-auto pt-4 border-t border-white/10">
<p class="text-[10px] text-white/40 uppercase mb-2">推荐匹配销售</p>
<div class="flex items-center gap-3">
<div class="w-8 h-8 rounded-full bg-parent-observing"></div>
<span class="text-sm font-bold text-white">亲和力高社交型销售</span>
</div>
</div>
</div>
</div>
</div>
<!-- Row 2 (Duplicates for the required 4-card grid layout as specified) -->
<!-- In a real app, these would be unique IDs, here we follow the 2-row x 4-
col request with the 4 defined personas -->
<div class="persona-card opacity-80" 
onclick="this.classList.toggle('flipped')">
<div class="persona-card-inner">
<div class="card-front bg-surface-dim border-parent-anxious/30 border-b-parent-
anxious p-6">
<div class="flex justify-between items-start mb-4">
<span class="px-3 py-1 rounded-lg bg-parent-anxious/20 text-parent-anxious 
font-bold text-[10px] tracking-widest border border-parent-anxious/30">P-
05</span>
<span class="material-symbols-outlined text-white/20">lock</span>
</div>
<div class="w-full h-48 bg-background/50 rounded-2xl mb-6 flex items-center 
justify-center overflow-hidden grayscale">
<img alt="张宝妈" class="h-40 w-40 object-contain" 
src="https://lh3.googleusercontent.com/aida/ADBb0ujtodUvUVt7GCpiBPHexAlVMsXVh2_
BzsMy6fzL0dzijwzvFROCdl5orj-kQYAQhr_U34cFVtZjce3AbJfoqJh5NnIxA3d1MRrme-
6x3Re_PJkDQ0zmaf0M9nLuF9t-4wTiTYOsw2K7HRgAtGkvjuYiq0DxxsoqKNfNa7y-dc-
C1VMwdZCbp9uMz6nI-_f3pp-6QuGdcuqTgHzqXS0ACU4QDy_-
VI7IlKgYmQhT30vaqNhjUPYa7l3zgrs"/>
</div>
<div class="text-center">
<h3 class="text-2xl font-black text-white mb-1">张宝妈 (进阶版)</h3>
<p class="text-white/40 font-bold text-xs">实战关卡 1-2 已锁定</p>
</div>
</div>
<div class="card-back bg-[#1e1e2d] border-parent-anxious border-b-parent-
anxious p-6">
<div class="flex flex-col items-center justify-center h-full text-center">
<span class="material-symbols-outlined text-4xl text-parent-anxious mb-
4">lock</span>
<p class="text-white font-bold mb-2">完成基础对练解锁</p>
<p class="text-sm text-outline-variant">需要 P-01 达成 3 星评分</p>
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
258
259
260
261
262
263
264


</div>
</div>
</div>
</div>
<div class="persona-card opacity-80" 
onclick="this.classList.toggle('flipped')">
<div class="persona-card-inner">
<div class="card-front bg-surface-dim border-parent-confused/30 border-b-
parent-confused p-6">
<div class="flex justify-between items-start mb-4">
<span class="px-3 py-1 rounded-lg bg-parent-confused/20 text-parent-confused 
font-bold text-[10px] tracking-widest border border-parent-confused/30">P-
06</span>
<span class="material-symbols-outlined text-white/20">lock</span>
</div>
<div class="w-full h-48 bg-background/50 rounded-2xl mb-6 flex items-center 
justify-center overflow-hidden grayscale">
<img alt="王宝爸" class="h-40 w-40 object-contain" 
src="https://lh3.googleusercontent.com/aida/ADBb0uj4Dw06TxBvUxvOeXR50kTaTaEpo-
nqRKL9YTzEZHk0CrPNqHkFiDVDr4GFhvNRohci4Wn6mvJ00G8kHfYlDvjZFqpnUsQY33okMC7wkAMBm
kbmAbz5Ix8dNK7RlA06EPXFRa8Y9wApNhLbo3nGmLoxTnAZIYM9QFeQVNYUqoyfmfdU-5-
Y3f4NSfAu99y5sIS8eOxH3Kgwldr3Ox4dwhLRCa15zWvwm5RukvefcwiR0ZgzgshIMZQ3Ip1-"/>
</div>
<div class="text-center">
<h3 class="text-2xl font-black text-white mb-1">王宝爸 (实战型)</h3>
<p class="text-white/40 font-bold text-xs">实战关卡 1-3 已锁定</p>
</div>
</div>
<div class="card-back bg-[#1e1e2d] border-parent-confused border-b-parent-
confused p-6">
<div class="flex flex-col items-center justify-center h-full text-center">
<span class="material-symbols-outlined text-4xl text-parent-confused mb-
4">lock</span>
<p class="text-white font-bold mb-2">完成基础对练解锁</p>
<p class="text-sm text-outline-variant">需要 P-02 达成 3 星评分</p>
</div>
</div>
</div>
</div>
<div class="persona-card opacity-80" 
onclick="this.classList.toggle('flipped')">
<div class="persona-card-inner">
<div class="card-front bg-surface-dim border-parent-rational/30 border-b-
parent-rational p-6">
<div class="flex justify-between items-start mb-4">
<span class="px-3 py-1 rounded-lg bg-parent-rational/20 text-parent-rational 
font-bold text-[10px] tracking-widest border border-parent-rational/30">P-
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
292
293
294
295
296
297


07</span>
<span class="material-symbols-outlined text-white/20">lock</span>
</div>
<div class="w-full h-48 bg-background/50 rounded-2xl mb-6 flex items-center 
justify-center overflow-hidden grayscale">
<img alt="李宝爸" class="h-40 w-40 object-contain" 
src="https://lh3.googleusercontent.com/aida/ADBb0uiuDNAXPsqNLuBn-98OREDzUBwLvK-
OEI9vHGSFkg4PIf_f9hKKtkD6Aj13pDsHfY3DTjtLDUN5sw1ae1PEM4GZCbW-
ngSBJabasxkAJ8CvikIKvsA4C8qGQhxZV_vSOkH75BYgtqkmcVdO_WSx_l5qAEhYjsOCtA8s3hrgGLJ
VcZR8imT8T11XSfeVv0XqlRaPQ2GxkmnzVxa91AQzQJi0eXYbhuJl3uzAVZLwq-qxDsOi6mvGx-
wgKSE"/>
</div>
<div class="text-center">
<h3 class="text-2xl font-black text-white mb-1">李宝爸 (专家型)</h3>
<p class="text-white/40 font-bold text-xs">实战关卡 1-4 已锁定</p>
</div>
</div>
<div class="card-back bg-[#1e1e2d] border-parent-rational border-b-parent-
rational p-6">
<div class="flex flex-col items-center justify-center h-full text-center">
<span class="material-symbols-outlined text-4xl text-parent-rational mb-
4">lock</span>
<p class="text-white font-bold mb-2">完成基础对练解锁</p>
<p class="text-sm text-outline-variant">需要 P-03 达成 3 星评分</p>
</div>
</div>
</div>
</div>
<div class="persona-card opacity-80" 
onclick="this.classList.toggle('flipped')">
<div class="persona-card-inner">
<div class="card-front bg-surface-dim border-parent-observing/30 border-b-
parent-observing p-6">
<div class="flex justify-between items-start mb-4">
<span class="px-3 py-1 rounded-lg bg-parent-observing/20 text-parent-observing 
font-bold text-[10px] tracking-widest border border-parent-observing/30">P-
08</span>
<span class="material-symbols-outlined text-white/20">lock</span>
</div>
<div class="w-full h-48 bg-background/50 rounded-2xl mb-6 flex items-center 
justify-center overflow-hidden grayscale">
<img alt="赵宝妈" class="h-40 w-40 object-contain" 
src="https://lh3.googleusercontent.com/aida/ADBb0ujCvWt9r7lUeRlvZKdHM9zqpBkstG0
eB_aEgOUElblDrLakBOUQVwpeQeX__RIYCrhLBZN9TrDbPuWSRJAeut_p0gc72file-
Me3aa0JDLIuGrlDbmu_B12d0hrz5poyssgV0ekf1BbvREjPnH3_afqU1seHwtH5DzduZQ7jroZax4qx
pwYfVhAEsd6R6LZoIOhR6sqcMfzQTmOtvIqHmZAxOPhVVZzVNIjgfaUByXOTFm_GmYyvP241zQ"/>
</div>
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


<div class="text-center">
<h3 class="text-2xl font-black text-white mb-1">赵宝妈 (终极关卡)</h3>
<p class="text-white/40 font-bold text-xs">实战关卡 1-5 已锁定</p>
</div>
</div>
<div class="card-back bg-[#1e1e2d] border-parent-observing border-b-parent-
observing p-6">
<div class="flex flex-col items-center justify-center h-full text-center">
<span class="material-symbols-outlined text-4xl text-parent-observing mb-
4">lock</span>
<p class="text-white font-bold mb-2">完成基础对练解锁</p>
<p class="text-sm text-outline-variant">需要 P-04 达成 3 星评分</p>
</div>
</div>
</div>
</div>
</div>
</div>
</div>
<!-- Floating Start Button -->
<div class="fixed bottom-10 right-10 z-50">
<button class="gamified-button group flex items-center gap-3 px-10 py-5 bg-
mascot-gold text-white rounded-3xl font-headline-md text-xl font-black shadow-
[0_10px_20px_rgba(255,159,28,0.4)] hover:scale-105 transition-all">
<span>开始实战演练</span>
<span class="material-symbols-outlined font-bold transition-transform group-
hover:translate-x-1">play_arrow</span>
</button>
</div>