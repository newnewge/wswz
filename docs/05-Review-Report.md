# 模块五：对练复盘报告（Review Report）

> 来源: 飞书文档「前端代码-松鼠ai培训助手前端界面」
> 模块: 对练复盘报告 · Module 5/9

---

文件：review-report.html · 含雷达图/进度条等评分可视化组件
① Tailwind Config 色板配置
代码块
<script id="tailwind-config">
  tailwind.config = {
    darkMode: "class",
    theme: {
      extend: {
        "colors": {
                "on-secondary-fixed-variant": "#753400",
                "primary-container": "#1e52d9",
                "secondary-fixed-dim": "#ffb68b",
                "parent-observing": "#718096",
                "secondary-container": "#fb7800",
                "parent-rational": "#10B981",
                "on-tertiary-fixed-variant": "#005236",
                "surface-dim": "#cfdaf2",
                "on-primary-container": "#cfd7ff",
                "parent-anxious": "#FF7A00",
                "surface-variant": "#d8e3fb",
                "primary-fixed-dim": "#b6c4ff",
                "surface-container": "#e7eeff",
                "on-surface": "#111c2d",
                "error-container": "#ffdad6",
                "parent-confused": "#00B2FF",
                "surface-tint": "#1d52d9",
                "mascot-gold": "#FFC800", // Adjusted for Duolingo feel
                "on-primary": "#ffffff",
                "surface-container-lowest": "#ffffff",
                "primary": "#003bb2",
                "on-secondary-fixed": "#321200",
                "on-primary-fixed-variant": "#003ab1",
                "error": "#ba1a1a",
                "on-primary-fixed": "#00164f",
                "tertiary-fixed": "#58CC02", // Duolingo Green
                "on-tertiary": "#ffffff",
                "background": "#0F172A",
                "tertiary-fixed-dim": "#46A302",
                "outline": "#747686",
                "tertiary-container": "#58CC02",
                "on-tertiary-container": "#ffffff",
                "primary-fixed": "#1CB0F6", // Duolingo Blue
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


                "failure-red": "#FF4B4B", // Duolingo Red
                "secondary-fixed": "#ffdbc8",
                "outline-variant": "#c4c5d7",
                "surface-container-high": "#dee8ff",
                "surface-container-low": "#f0f3ff",
                "secondary": "#994700",
                "on-error-container": "#93000a",
                "inverse-surface": "#263143",
                "surface": "#f9f9ff",
                "on-background": "#111c2d",
                "on-error": "#ffffff",
                "on-secondary-container": "#ffffff",
                "inverse-primary": "#b6c4ff",
                "surface-container-highest": "#d8e3fb",
                "on-secondary": "#ffffff",
                "surface-bright": "#f9f9ff",
                "inverse-on-surface": "#ecf1ff",
                "on-tertiary-fixed": "#ffffff",
                "on-surface-variant": "#434654",
                "surface-bg": "#F8FAFC",
                "tertiary": "#58CC02"
        },
        "borderRadius": {
                "DEFAULT": "0.25rem",
                "lg": "0.75rem",
                "xl": "1.25rem",
                "2xl": "1.5rem",
                "full": "9999px"
        },
        "spacing": {
                "stack-sm": "8px",
                "gutter": "16px",
                "card-padding": "24px",
                "stack-md": "16px",
                "container-margin": "24px",
                "unit": "8px"
        },
        "fontFamily": {
                "label-caps": [
                        "Inter", "sans-serif"
                ],
                "headline-lg": [
                        "Hanken Grotesk", "sans-serif"
                ],
                "headline-lg-mobile": [
                        "Hanken Grotesk", "sans-serif"
                ],
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


                "body-base": [
                        "Inter", "sans-serif"
                ],
                "headline-md": [
                        "Hanken Grotesk", "sans-serif"
                ],
                "body-lg": [
                        "Inter", "sans-serif"
                ],
                "annotation-italic": [
                        "Inter", "sans-serif"
                ],
                "display": [
                        "ZCOOL KuaiLe", "cursive"
                ]
        },
        "fontSize": {
                "label-caps": [
                        "12px",
                        {
                                "lineHeight": "16px",
                                "letterSpacing": "0.05em",
                                "fontWeight": "700"
                        }
                ],
                "headline-lg": [
                        "32px",
                        {
                                "lineHeight": "40px",
                                "fontWeight": "800"
                        }
                ],
                "headline-lg-mobile": [
                        "24px",
                        {
                                "lineHeight": "32px",
                                "fontWeight": "800"
                        }
                ],
                "body-base": [
                        "15px",
                        {
                                "lineHeight": "24px",
                                "fontWeight": "600"
                        }
                ],
                "headline-md": [
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


                        "20px",
                        {
                                "lineHeight": "28px",
                                "fontWeight": "700"
                        }
                ],
                "body-lg": [
                        "18px",
                        {
                                "lineHeight": "26px",
                                "fontWeight": "600"
                        }
                ],
                "annotation-italic": [
                        "12px",
                        {
                                "lineHeight": "16px",
                                "fontWeight": "500"
                        }
                ]
        },
        "boxShadow": {
            "bouncy": "0 4px 0 0 rgba(0,0,0,0.2)",
            "bouncy-sm": "0 2px 0 0 rgba(0,0,0,0.2)",
            "bouncy-green": "0 4px 0 0 #46A302",
            "bouncy-orange": "0 4px 0 0 #e66a00",
            "bouncy-blue": "0 4px 0 0 #1899D6",
            "bouncy-yellow": "0 4px 0 0 #DDA900",
            "bouncy-red": "0 4px 0 0 #E53935",
        }
},
    },
  }
</script>
② Custom CSS 样式（含图表动画）
代码块

    /* Custom styles for gamified look */
    .btn-bouncy {
        transition: transform 0.1s, box-shadow 0.1s;
    }
    .btn-bouncy:active {
        transform: translateY(4px);
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
166
167
1
2
3
4
5
6
7


        box-shadow: 0 0px 0 0 transparent !important;
    }
    .card-bouncy {
        border-bottom-width: 4px;
        border-bottom-color: rgba(0,0,0,0.3);
    }

③ Report Body 报告主体结构
代码块
</nav>
</aside>
<!-- Main Content Area -->
<main class="flex-1 overflow-y-auto w-full py-10 px-6 md:px-12 flex flex-col 
items-center">
<div class="max-w-6xl w-full flex flex-col gap-stack-md">
<!-- Header Section -->
<div class="text-center mb-6">
<h1 class="font-display text-4xl mb-2 text-mascot-gold drop-shadow-md tracking-
wider">对练复盘报告</h1>
<p class="font-body-lg text-primary-fixed font-bold">太棒了！您完成了一次实战对练！
</p>
</div>
<!-- Main Layout: 2 Columns -->
<div class="grid grid-cols-1 lg:grid-cols-12 gap-gutter w-full">
<!-- Left Column: Overview & Radar -->
<div class="lg:col-span-4 flex flex-col gap-gutter">
<!-- Overview Card -->
<div class="bg-[#1E293B] rounded-2xl p-card-padding border-2 border-[#334155] 
shadow-bouncy relative overflow-hidden flex flex-col items-center text-center">
<div class="absolute -top-10 -right-10 w-40 h-40 bg-primary-fixed/10 rounded-
full blur-2xl"></div>
<h2 class="font-headline-md text-headline-md mb-6 text-white w-full text-left 
flex items-center gap-2">
<span class="material-symbols-outlined text-primary-fixed">star</span>
    概览信息
</h2>
<!-- Gamification & Score -->
<div class="relative w-48 h-48 flex items-center justify-center mb-6">
<!-- Silver Medal Badge -->
<div class="absolute -top-2 -right-2 z-20 flex flex-col items-center">
<div class="w-14 h-14 rounded-full bg-gradient-to-br from-[#E0E0E0] to-
[#9E9E9E] border-4 border-[#1E293B] flex items-center justify-center shadow-
[0_4px_0_0_rgba(0,0,0,0.5)] transform rotate-12">
8
9
10
11
12
13
14
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


<span class="material-symbols-outlined text-white text-3xl drop-shadow-md" 
data-icon="military_tech" style="font-variation-settings: 'FILL' 
1;">military_tech</span>
</div>
<span class="font-label-caps text-[12px] text-white mt-1 bg-[#1E293B] px-2 py-
0.5 rounded-full border border-[#334155]">银牌表现</span>
</div>
<!-- Circular Progress -->
<svg class="absolute inset-0 w-full h-full transform -rotate-90" viewbox="0 0 
100 100">
<circle class="text-[#334155]" cx="50" cy="50" fill="none" r="44" 
stroke="currentColor" stroke-width="12"></circle>
<circle class="text-tertiary-fixed drop-shadow-md" cx="50" cy="50" fill="none" 
r="44" stroke="currentColor" stroke-dasharray="276.46" stroke-
dashoffset="41.47" stroke-linecap="round" stroke-width="12"></circle>
</svg>
<div class="flex flex-col items-center z-10 bg-[#1E293B] w-32 h-32 rounded-
full justify-center shadow-inner">
<span class="font-display text-5xl font-black text-tertiary-fixed drop-shadow-
sm">85</span>
<span class="font-label-caps text-outline-variant mt-1">综合得分</span>
</div>
</div>
<!-- Target Details -->
<div class="w-full flex flex-col gap-4">
<div class="flex items-center gap-4 p-4 bg-[#334155]/50 rounded-xl border-2 
border-[#475569] shadow-bouncy-sm">
<div class="w-12 h-12 rounded-xl bg-primary-fixed/20 flex items-center justify-
center text-primary-fixed">
<span class="material-symbols-outlined text-2xl" data-icon="book" style="font-
variation-settings: 'FILL' 1;">book</span>
</div>
<div class="text-left">
<div class="font-label-caps text-outline-variant">对练场景</div>
<div class="font-body-lg font-bold text-white">S-01 破冰</div>
</div>
</div>
<div class="flex items-center gap-4 p-4 bg-[#334155]/50 rounded-xl border-2 
border-[#475569] shadow-bouncy-sm">
<div class="w-12 h-12 rounded-full overflow-hidden border-2 border-parent-
anxious bg-white/10 p-1">
<img alt="对练对象头像" class="w-full h-full object-cover rounded-full" 
src="https://lh3.googleusercontent.com/aida-
public/AB6AXuDNsBBfMIu2IOMvgEDwncs1k6XGl75vO9iPP-
oQmNYWtHE_9firYZDQve0fZaJOpk9Y3P7X3ji9jlFqYD83E5EK4gGXWgfsN60NmXLbPbyDmXoQ-
BbEDz5KKs8CfdboepvqFwwxTeI0o_s2C4Jo5ljGeYwTNghzMcXj9gxSwGqJ-
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


dd_6krr9NIoRDpzPG0XJA3q7cp7WrD_Bntc0l1bpnO2VCk3GO_tbzzSCQhoYQHF-
N28f6YQKeCC9r5gM71CdB57PoVSEvNs3haw"/>
</div>
<div class="text-left">
<div class="font-label-caps text-outline-variant">对练对象</div>
<div class="flex items-center gap-2">
<span class="font-body-lg font-bold text-white">张宝妈</span>
<span class="px-2 py-1 rounded-lg bg-parent-anxious text-white font-label-caps 
shadow-sm">焦虑型</span>
</div>
</div>
</div>
</div>
</div>
<!-- Radar Chart Card -->
<div class="bg-[#1E293B] rounded-2xl p-card-padding border-2 border-[#334155] 
shadow-bouncy flex flex-col items-center justify-center">
<h2 class="font-headline-md text-headline-md mb-4 w-full text-left text-white 
flex items-center gap-2">
<span class="material-symbols-outlined text-primary-fixed">radar</span>
    能力分析
</h2>
<div class="relative w-full aspect-square max-w-[220px] flex items-center 
justify-center bg-[#334155]/30 rounded-full border-4 border-[#475569]/50 my-4 
shadow-inner">
<!-- Placeholder Radar Graphics -->
<div class="absolute inset-0 border-2 border-[#475569]/50 rounded-full m-4">
</div>
<div class="absolute inset-0 border-2 border-[#475569]/50 rounded-full m-8">
</div>
<div class="absolute inset-0 border-2 border-[#475569]/50 rounded-full m-12">
</div>
<svg class="absolute inset-0 w-full h-full opacity-80 drop-shadow-md" 
viewbox="0 0 100 100">
<polygon fill="rgba(28,176,246,0.4)" points="50,15 85,35 80,75 50,90 20,75 
15,35" stroke="#1CB0F6" stroke-linejoin="round" stroke-width="3"></polygon>
</svg>
<div class="absolute w-12 h-12 bg-[#1E293B] rounded-full border-2 border-
primary-fixed flex items-center justify-center z-10 shadow-md">
<span class="material-symbols-outlined text-primary-fixed text-xl" data-
icon="insights" style="font-variation-settings: 'FILL' 1;">insights</span>
</div>
</div>
<div class="mt-4 flex flex-wrap justify-center gap-2 w-full">
<span class="text-xs px-3 py-1.5 bg-[#334155] rounded-xl text-white font-bold 
border-b-2 border-[#0F172A]">共情力</span>
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


<span class="text-xs px-3 py-1.5 bg-[#334155] rounded-xl text-white font-bold 
border-b-2 border-[#0F172A]">需求挖掘</span>
<span class="text-xs px-3 py-1.5 bg-[#334155] rounded-xl text-white font-bold 
border-b-2 border-[#0F172A]">产品链接</span>
<span class="text-xs px-3 py-1.5 bg-[#334155] rounded-xl text-white font-bold 
border-b-2 border-[#0F172A]">异议处理</span>
</div>
</div>
</div>
<!-- Right Column: Detailed Evaluation -->
<div class="lg:col-span-8 flex flex-col gap-gutter">
<!-- Scoring Table Card -->
<div class="bg-[#1E293B] rounded-2xl p-card-padding border-2 border-[#334155] 
shadow-bouncy overflow-hidden">
<h2 class="font-headline-md text-headline-md mb-6 text-white flex items-center 
gap-2">
<span class="material-symbols-outlined text-tertiary-fixed" data-
icon="format_list_bulleted">format_list_bulleted</span>
                            详细评分表
                        </h2>
<div class="overflow-x-auto">
<table class="w-full text-left border-collapse">
<thead>
<tr class="border-b-2 border-[#334155]">
<th class="py-3 px-4 font-label-caps text-outline-variant">考核维度</th>
<th class="py-3 px-4 font-label-caps text-outline-variant">满分</th>
<th class="py-3 px-4 font-label-caps text-outline-variant">您的得分</th>
<th class="py-3 px-4 font-label-caps text-outline-variant">表现评级</th>
</tr>
</thead>
<tbody>
<tr class="border-b-2 border-[#334155]/50 hover:bg-[#334155]/30 transition-
colors">
<td class="py-4 px-4 font-body-base text-white font-bold flex items-center gap-
2">
<span class="material-symbols-outlined text-tertiary-fixed text-
lg">check_circle</span>
    开场破冰与情绪安抚
</td>
<td class="py-4 px-4 font-body-base text-outline-variant font-bold">30</td>
<td class="py-4 px-4 font-display text-2xl text-tertiary-fixed drop-shadow-
sm">28</td>
<td class="py-4 px-4"><span class="px-3 py-1 text-sm font-bold rounded-xl bg-
tertiary-fixed text-white border-b-2 border-tertiary-fixed-dim shadow-sm">优秀!
</span></td>
</tr>
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
114
115
116
117
118
119


<tr class="border-b-2 border-[#334155]/50 hover:bg-[#334155]/30 transition-
colors">
<td class="py-4 px-4 font-body-base text-white font-bold flex items-center gap-
2">
<span class="material-symbols-outlined text-mascot-gold text-
lg">thumb_up</span>
    痛点挖掘与共情
</td>
<td class="py-4 px-4 font-body-base text-outline-variant font-bold">40</td>
<td class="py-4 px-4 font-display text-2xl text-mascot-gold drop-shadow-
sm">32</td>
<td class="py-4 px-4"><span class="px-3 py-1 text-sm font-bold rounded-xl bg-
mascot-gold text-[#592600] border-b-2 border-[#DDA900] shadow-sm">良好</span>
</td>
</tr>
<tr class="hover:bg-[#334155]/30 transition-colors">
<td class="py-4 px-4 font-body-base text-white font-bold flex items-center gap-
2">
<span class="material-symbols-outlined text-failure-red text-
lg">trending_up</span>
    产品价值自然引入
</td>
<td class="py-4 px-4 font-body-base text-outline-variant font-bold">30</td>
<td class="py-4 px-4 font-display text-2xl text-failure-red drop-shadow-
sm">25</td>
<td class="py-4 px-4"><span class="px-3 py-1 text-sm font-bold rounded-xl bg-
failure-red text-white border-b-2 border-[#C62828] shadow-sm">加油</span></td>
</tr>
</tbody>
</table>
</div>
</div>
<!-- Highlights & Missing Items -->
<div class="grid grid-cols-1 md:grid-cols-2 gap-gutter">
<!-- Highlights -->
<div class="bg-tertiary-fixed/10 rounded-2xl p-card-padding border-2 border-
tertiary-fixed/30 relative shadow-bouncy-sm">
<div class="flex items-center gap-2 mb-4">
<div class="w-10 h-10 rounded-xl bg-tertiary-fixed text-white flex items-
center justify-center shadow-bouncy-green transform -rotate-6">
<span class="material-symbols-outlined text-2xl" data-icon="celebration" 
style="font-variation-settings: 'FILL' 1;">celebration</span>
</div>
<h3 class="font-headline-md text-tertiary-fixed font-bold">做得真棒！</h3>
</div>
<ul class="space-y-3">
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


<li class="flex items-start gap-3 font-body-base text-white/90 bg-[#1E293B] p-
3 rounded-xl border border-[#334155]">
<span class="material-symbols-outlined text-tertiary-fixed text-xl bg-tertiary-
fixed/20 rounded-full p-0.5">check</span>
    准确识别了家长的核心焦虑源于孩子的注意力不集中。
</li>
<li class="flex items-start gap-3 font-body-base text-white/90 bg-[#1E293B] p-
3 rounded-xl border border-[#334155]">
<span class="material-symbols-outlined text-tertiary-fixed text-xl bg-tertiary-
fixed/20 rounded-full p-0.5">check</span>
    语气平稳，开场迅速拉近了距离。
</li>
</ul>
</div>
<!-- Missing Items -->
<div class="bg-mascot-gold/10 rounded-2xl p-card-padding border-2 border-
mascot-gold/30 relative shadow-bouncy-sm">
<div class="flex items-center gap-2 mb-4">
<div class="w-10 h-10 rounded-xl bg-mascot-gold text-[#592600] flex items-
center justify-center shadow-bouncy-yellow transform rotate-6">
<span class="material-symbols-outlined text-2xl" data-icon="lightbulb" 
style="font-variation-settings: 'FILL' 1;">lightbulb</span>
</div>
<h3 class="font-headline-md text-mascot-gold font-bold">继续保持，尝试这些：</h3>
</div>
<ul class="space-y-3">
<li class="flex items-start gap-3 font-body-base text-white/90 bg-[#1E293B] p-
3 rounded-xl border border-[#334155]">
<span class="material-symbols-outlined text-mascot-gold text-xl bg-mascot-
gold/20 rounded-full p-0.5">arrow_forward</span>
    在安抚后顺势抛出关于学习习惯的具体提问，效果会更好哦。
</li>
<li class="flex items-start gap-3 font-body-base text-white/90 bg-[#1E293B] p-
3 rounded-xl border border-[#334155]">
<span class="material-symbols-outlined text-mascot-gold text-xl bg-mascot-
gold/20 rounded-full p-0.5">arrow_forward</span>
    引入产品前可以多做一点场景铺垫，让过渡更自然。
</li>
</ul>
</div>
</div>
<!-- Master Liu Focus Card -->
<div class="bg-[#1CB0F6] rounded-2xl p-1 relative shadow-bouncy-blue mt-4">
<div class="bg-[#1E293B] rounded-xl p-card-padding relative overflow-visible 
flex flex-col md:flex-row gap-stack-md items-center">
<!-- Coach Bubble Tail -->
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


<div class="hidden md:block absolute -left-3 top-1/2 transform -translate-y-
1/2 w-6 h-6 bg-[#1E293B] border-l-2 border-b-2 border-[#1CB0F6] rotate-45">
</div>
<div class="w-full md:w-1/4 flex flex-col items-center justify-center relative 
z-10 md:-ml-8 md:-mt-8">
<div class="w-32 h-32 bg-white rounded-full flex items-center justify-center 
border-4 border-[#1CB0F6] shadow-bouncy-blue overflow-hidden p-2 transform -
rotate-3 hover:rotate-0 transition-transform">
<img alt="导师刘总" class="w-full h-full object-cover rounded-full" 
src="https://lh3.googleusercontent.com/aida/ADBb0uj8TuiAgS9y8yo4zD_Azu8mnDVCkdc
5ENHhK3-AQCNuRIPn4SrCXdG8nr53RTBA_OC_EDCl79Od7-d5OMgEAvMp2TQcygsx2XESub-
sRsHMFbB-
bbSYHyYbCnZPG9XdRi_1dcQSrNR3xbokzfjqo0SApaLCHGXXWRotPME_hvAAvFDnxYW7WLDpQ_tspPL
06PFxAL-n8y0rRhRX6mYAWwi-KSNLFgDeZmjTCOQbFFNYfaREBKusZoMhJKc"/>
</div>
<div class="mt-[-12px] bg-mascot-gold text-[#592600] font-bold px-3 py-1 
rounded-xl text-sm border-2 border-white shadow-sm z-20">刘总教练</div>
</div>
<div class="w-full md:w-3/4 flex flex-col gap-stack-sm justify-center pl-4">
<h4 class="font-display text-2xl text-white mb-2 flex items-center gap-2 
tracking-wide">
<span class="material-symbols-outlined text-mascot-gold text-3xl" data-
icon="tips_and_updates" style="font-variation-settings: 'FILL' 
1;">tips_and_updates</span>
    划个重点！
</h4>
<div class="bg-[#334155]/50 rounded-xl p-5 border-2 border-[#475569] text-
white font-body-lg leading-relaxed shadow-inner">
    在过渡到产品介绍时略显生硬。建议在安抚后，先通过提问深挖焦虑背后的具体原因（例如：
<strong class="text-mascot-gold">“平时在家写作业会经常走神吗？”</strong>），等家长给
出确认反馈后，再自然引出产品在专注力培养上的价值。
</div>
</div>
</div>
</div>
</div>
</div>
<!-- Action Buttons -->
<div class="flex justify-end gap-6 mt-8 w-full border-t-2 border-[#334155] pt-
8">
<button class="px-8 py-4 rounded-2xl font-body-lg font-bold border-2 border-
[#475569] text-white bg-[#334155] hover:bg-[#475569] shadow-bouncy btn-bouncy">
    返回场景库
</button>
<button class="px-8 py-4 rounded-2xl font-body-lg font-bold bg-secondary-
container text-white border-2 border-secondary hover:bg-[#e66a00] shadow-
bouncy-orange btn-bouncy flex items-center gap-2">
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


    再练一次！
    <span class="material-symbols-outlined">refresh</span>
</button>
</div>
</div>