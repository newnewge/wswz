# 模块六：场景对练库（Scenario Library）

> 来源: 飞书文档「前端代码-松鼠ai培训助手前端界面」
> 模块: 场景对练库 · Module 6/9

---

文件：scenario-library.html · 游戏化卡片场景体系
① Tailwind Config 色板配置
代码块
<script id="tailwind-config">
        tailwind.config = {
            darkMode: "class",
            theme: {
                extend: {
                    "colors": {
                        "brand-orange": "#ff9900",
                        "deep-navy": "#001a4d",
                        "card-navy": "#0a265c",
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
213
214
215
216
217
218
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


                        "surface-container-lowest": "#ffffff",
                        "primary-container": "#1e52d9",
                        "parent-rational": "#10B981",
                        "tertiary": "#005237",
                        "primary-fixed-dim": "#b6c4ff",
                        "background": "#f9f9ff",
                        "surface-dim": "#cfdaf2",
                        "on-secondary-container": "#592600",
                        "secondary-fixed": "#ffdbc8",
                        "surface-container-highest": "#d8e3fb",
                        "primary-fixed": "#dce1ff",
                        "parent-anxious": "#FF7A00",
                        "secondary-container": "#fb7800",
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
                        "on-background": "#111c2d",
                        "surface-container": "#e7eeff",
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
                        "headline-lg-mobile": ["24px", { "lineHeight": "32px", 
"fontWeight": "700" }],
                        "body-lg": ["16px", { "lineHeight": "24px", 
"fontWeight": "400" }],
                        "label-caps": ["12px", { "lineHeight": "16px", 
"letterSpacing": "0.05em", "fontWeight": "600" }],
                        "headline-md": ["20px", { "lineHeight": "28px", 
"fontWeight": "600" }],
                        "headline-lg": ["32px", { "lineHeight": "40px", 
"fontWeight": "700" }],
                        "body-base": ["14px", { "lineHeight": "22px", 
"fontWeight": "400" }],
                        "annotation-italic": ["12px", { "lineHeight": "16px", 
"fontWeight": "400" }]
                    }
                }
            }
        }
    </script>
② Custom CSS 样式（含游戏卡片动效）
代码块

        .gamified-card {
            background: #0a265c;
            border-bottom-width: 4px;
            border-color: rgba(255, 255, 255, 0.1);
            transition: all 0.2s ease;
        }
        .gamified-card:hover {
            transform: translateY(-2px);
            border-bottom-width: 6px;
        }
        .gamified-card.active {
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


            border-color: #ff9900;
        }
        .sub-item {
            background: rgba(255, 255, 255, 0.05);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }
        .sub-item:hover {
            background: rgba(255, 255, 255, 0.1);
        }
        .mentor-float {
            animation: float 3s ease-in-out infinite;
        }
        @keyframes float {
            0% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
            100% { transform: translateY(0px); }
        }

③ Navigation 侧边导航
代码块
<nav class="bg-brand-orange h-full w-64 fixed left-0 top-0 flex flex-col p-
stack-md shrink-0 z-50 border-r border-white/10 hidden md:flex">
<!-- Brand -->
<div class="mb-10 px-2 flex flex-col gap-4">
<div class="h-14 flex items-center">
<img alt="Squirrel AI" class="h-12 object-contain" 
src="https://lh3.googleusercontent.com/aida-
public/AB6AXuDqe4YTJTKEP3yBcdEwZPaZGuvuB7gaL8ZgLkIDWtauuzDdyR8CCickDEATCf9q7CJ8
zNqK6lmhDP4T1DkE0zLHJXumx_5zMh5pp9Us5b6yTn3CmFlsU5_xuIfnQVZp2tpbJ-
PXCD4PoFL8MIldnFbj7YAHaM3QpK0oelSnELToSCIHaK-INnxNhWo26QBlyM4jDhTcjRkym-
vjk9C3lloJKg_AiJqY7PtPLr-h3Cm_mjYjyy3BeUCOfUOUy3GHlR6jbHeyqMDjZ3Pa">
</div>

</div>
<!-- Main Navigation -->
<div class="flex-1 space-y-2">
<a class="flex items-center gap-3 px-4 py-3 rounded-xl bg-white/20 text-white 
font-bold transition-all duration-200" href="#">
<span class="material-symbols-outlined" data-icon="menu_book" style="font-
variation-settings: 'FILL' 1;">menu_book</span>
<span class="font-body-base text-body-base">场景对练库</span>
</a>
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


<a class="flex items-center gap-3 px-4 py-3 rounded-xl text-white/90 hover:bg-
white/10 transition-colors duration-200" href="#">
<span class="material-symbols-outlined" data-
icon="person_search">person_search</span>
<span class="font-body-base text-body-base">角色库</span>
</a>
<a class="flex items-center gap-3 px-4 py-3 rounded-xl text-white/90 hover:bg-
white/10 transition-colors duration-200" href="#">
<span class="material-symbols-outlined" data-icon="history">history</span>
<span class="font-body-base text-body-base">对练历史</span>
</a>
<a class="flex items-center gap-3 px-4 py-3 rounded-xl text-white/90 hover:bg-
white/10 transition-colors duration-200" href="#">
<span class="material-symbols-outlined" data-icon="dashboard">dashboard</span>
<span class="font-body-base text-body-base">团队看板</span>
</a>
</div>
<!-- Footer Navigation -->
<div class="space-y-2 border-t border-white/20 pt-4 mt-auto">
<a class="flex items-center gap-3 px-4 py-2 rounded-lg text-white/80 hover:bg-
white/10 transition-colors" href="#">
<span class="material-symbols-outlined" data-icon="settings">settings</span>
<span class="font-body-base text-body-base">设置</span>
</a>
<a class="flex items-center gap-3 px-4 py-2 rounded-lg text-white/80 hover:bg-
white/10 transition-colors" href="#">
<span class="material-symbols-outlined" data-icon="help">help</span>
<span class="font-body-base text-body-base">帮助中心</span>
</a>
</div>
</nav>
④ Scenario Cards 场景卡片区
代码块
</nav>
<!-- Main Content Area -->
<div class="flex-1 flex flex-col md:ml-64 h-full">
<!-- TopAppBar -->
<header class="bg-deep-navy/80 backdrop-blur-md sticky top-0 z-40 flex justify-
between items-center w-full px-container-margin py-stack-sm h-16 shrink-0 
border-b border-white/5">
<div class="flex items-center gap-4">
<h2 class="font-headline-md text-headline-md font-bold text-white hidden 
md:block">松鼠AI销售培训</h2>
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
1
2
3
4
5
6
7


<button class="md:hidden p-2 text-white">
<span class="material-symbols-outlined text-2xl" data-icon="menu">menu</span>
</button>
</div>
<div class="flex items-center gap-4">
<div class="relative hidden sm:block">
<span class="material-symbols-outlined absolute left-3 top-1/2 -translate-y-
1/2 text-white/40" data-icon="search">search</span>
<input class="pl-10 pr-4 py-2 bg-white/5 rounded-full text-body-base border 
border-white/10 focus:ring-2 focus:ring-brand-orange w-64 text-white 
placeholder-white/40 outline-none" placeholder="搜索练习场景..." type="text">
</div>
<button class="p-2 text-white/70 hover:text-white transition-colors relative">
<span class="material-symbols-outlined" data-
icon="notifications">notifications</span>
<span class="absolute top-2 right-2 w-2 h-2 bg-failure-red rounded-full">
</span>
</button>
<div class="flex items-center gap-2 bg-white/5 px-3 py-1.5 rounded-full border 
border-white/10">
<span class="material-symbols-outlined text-mascot-gold" data-icon="stars" 
style="font-variation-settings: 'FILL' 1;">stars</span>
<span class="font-bold text-sm">1,250 积分</span>
</div>
<div class="w-10 h-10 rounded-full overflow-hidden border-2 border-brand-
orange cursor-pointer">
<img alt="User Avatar" class="w-full h-full object-cover" 
src="https://lh3.googleusercontent.com/aida-
public/AB6AXuCkTlGpv3tno1q2rZcwaPLAnqSqGjR-4SGiwW6vb4hjanNiqDBs-
xnbW6nMXRnNYQyGLUtZPerHgCuT8NWbvs7_YRlTl_cPkDOd0koAg_WEihKSB-
gIdp3o6gh4EvkE08r5y-FQ1Zt-
_NkA0MHJrOfDTF61m7d2ALfI6sVA7fcTK8WEvQp9v0N64ncLij5ElHRGFsmLdl45bfNbGv8-
thez_GegJvylvukIJ6rncEq7t9p8lh7tx1jpWewf3j7sEF88rTn0nfK-tegz">
</div>
</div>
</header>
<!-- Canvas -->
<main class="flex-1 overflow-y-auto p-container-margin md:p-10 flex flex-col 
gap-10">
<!-- Header -->
<div class="relative">
<h1 class="font-headline-lg text-headline-lg text-white mb-2">场景对练库</h1>
<p class="text-white/60 max-w-2xl font-body-lg">欢迎来到大师练兵场。在这里，我们将模
拟真实的销售场景，助你一步步成为顶尖销售。请按顺序解锁关卡。</p>
<!-- Floating Master Liu -->
<div class="absolute -top-4 right-0 lg:right-10 flex flex-col items-center">
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


<div class="mentor-float w-24 h-24 rounded-full border-4 border-brand-orange 
bg-white overflow-hidden shadow-2xl mb-2">
<img alt="Master Liu" class="w-full h-full object-cover" 
src="https://lh3.googleusercontent.com/aida/ADBb0uj8TuiAgS9y8yo4zD_Azu8mnDVCkdc
5ENHhK3-AQCNuRIPn4SrCXdG8nr53RTBA_OC_EDCl79Od7-d5OMgEAvMp2TQcygsx2XESub-
sRsHMFbB-
bbSYHyYbCnZPG9XdRi_1dcQSrNR3xbokzfjqo0SApaLCHGXXWRotPME_hvAAvFDnxYW7WLDpQ_tspPL
06PFxAL-n8y0rRhRX6mYAWwi-KSNLFgDeZmjTCOQbFFNYfaREBKusZoMhJKc">
</div>
<div class="bg-white text-deep-navy px-4 py-2 rounded-xl text-xs font-bold 
shadow-lg relative after:content-[''] after:absolute after:-top-2 after:left-
1/2 after:-translate-x-1/2 after:border-l-8 after:border-l-transparent 
after:border-r-8 after:border-r-transparent after:border-b-8 after:border-b-
white">
                        “徒儿，今日宜攻克‘需求挖掘’”
                    </div>
</div>
</div>
<!-- Stage Grid -->
<div class="grid grid-cols-1 xl:grid-cols-2 gap-8">
<!-- S-01 Stage (Completed) -->
<div class="gamified-card rounded-2xl p-6 flex flex-col gap-6">
<div class="flex justify-between items-center">
<div class="flex items-center gap-4">
<div class="w-14 h-14 rounded-2xl bg-parent-rational/20 border border-parent-
rational/30 flex items-center justify-center">
<span class="material-symbols-outlined text-parent-rational text-3xl" data-
icon="handshake" style="font-variation-settings: 'FILL' 1;">handshake</span>
</div>
<div>
<h3 class="text-xl font-black">S-01 破冰与建立信任</h3>
<div class="flex gap-1 text-mascot-gold mt-1">
<span class="material-symbols-outlined text-sm" data-icon="star" style="font-
variation-settings: 'FILL' 1;">star</span>
<span class="material-symbols-outlined text-sm" data-icon="star" style="font-
variation-settings: 'FILL' 1;">star</span>
<span class="material-symbols-outlined text-sm" data-icon="star" style="font-
variation-settings: 'FILL' 1;">star</span>
</div>
</div>
</div>
<span class="bg-parent-rational/10 text-parent-rational px-3 py-1 rounded-full 
text-xs font-bold uppercase tracking-wider border border-parent-rational/20">已
通关</span>
</div>
<!-- Sub-scenarios -->
<div class="grid grid-cols-1 md:grid-cols-2 gap-3">
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
66
67


<div class="sub-item rounded-xl p-3 flex items-center justify-between cursor-
pointer">
<span class="text-sm font-semibold">1.1 初次见面：张宝妈</span>
<span class="material-symbols-outlined text-parent-rational" data-
icon="check_circle" style="font-variation-settings: 'FILL' 
1;">check_circle</span>
</div>
<div class="sub-item rounded-xl p-3 flex items-center justify-between cursor-
pointer">
<span class="text-sm font-semibold">1.2 应对犹豫：李宝爸</span>
<span class="material-symbols-outlined text-parent-rational" data-
icon="check_circle" style="font-variation-settings: 'FILL' 
1;">check_circle</span>
</div>
<div class="sub-item rounded-xl p-3 flex items-center justify-between cursor-
pointer">
<span class="text-sm font-semibold">1.3 社区拓客：李老师</span>
<span class="material-symbols-outlined text-parent-rational" data-
icon="check_circle" style="font-variation-settings: 'FILL' 
1;">check_circle</span>
</div>
<div class="sub-item rounded-xl p-3 flex items-center justify-between cursor-
pointer bg-white/10 border-white/20">
<span class="text-sm font-semibold">1.4 综合演练</span>
<span class="material-symbols-outlined text-parent-rational" data-
icon="check_circle" style="font-variation-settings: 'FILL' 
1;">check_circle</span>
</div>
</div>
</div>
<!-- S-02 Stage (Active) -->
<div class="gamified-card active rounded-2xl p-6 flex flex-col gap-6">
<div class="flex justify-between items-center">
<div class="flex items-center gap-4">
<div class="w-14 h-14 rounded-2xl bg-brand-orange/20 border border-brand-
orange/30 flex items-center justify-center">
<span class="material-symbols-outlined text-brand-orange text-3xl" data-
icon="search_insights">search_insights</span>
</div>
<div>
<h3 class="text-xl font-black">S-02 深度需求挖掘</h3>
<div class="flex gap-1 text-white/30 mt-1">
<span class="material-symbols-outlined text-sm" data-icon="star" style="font-
variation-settings: 'FILL' 1;">star</span>
<span class="material-symbols-outlined text-sm text-brand-orange" data-
icon="star_half">star_half</span>
<span class="material-symbols-outlined text-sm" data-icon="star">star</span>
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


</div>
</div>
</div>
<span class="bg-brand-orange text-white px-3 py-1 rounded-full text-xs font-
bold uppercase tracking-wider animate-pulse">进行中</span>
</div>
<!-- Sub-scenarios -->
<div class="grid grid-cols-1 md:grid-cols-2 gap-3">
<div class="sub-item rounded-xl p-3 flex items-center justify-between cursor-
pointer border-brand-orange/50 bg-white/10">
<span class="text-sm font-semibold">2.1 痛点追问：王宝妈</span>
<span class="material-symbols-outlined text-brand-orange animate-spin" data-
icon="sync" style="font-size: 18px">sync</span>
</div>
<div class="sub-item rounded-xl p-3 flex items-center justify-between cursor-
pointer opacity-60">
<span class="text-sm font-semibold">2.2 学习目标设定</span>
<span class="material-symbols-outlined text-white/40" data-icon="lock" 
style="font-size: 18px">lock</span>
</div>
<div class="sub-item rounded-xl p-3 flex items-center justify-between cursor-
pointer opacity-60">
<span class="text-sm font-semibold">2.3 测评反馈面谈</span>
<span class="material-symbols-outlined text-white/40" data-icon="lock" 
style="font-size: 18px">lock</span>
</div>
<div class="sub-item rounded-xl p-3 flex items-center justify-between cursor-
pointer opacity-60">
<span class="text-sm font-semibold">2.4 需求匹配方案</span>
<span class="material-symbols-outlined text-white/40" data-icon="lock" 
style="font-size: 18px">lock</span>
</div>
</div>
<div class="mt-2">
<button class="w-full py-3 bg-brand-orange hover:bg-brand-orange/90 text-white 
font-bold rounded-xl transition-all shadow-lg active:scale-[0.98]">
                            继续 2.1 挑战
                        </button>
</div>
</div>
<!-- S-03 Stage (Locked) -->
<div class="gamified-card rounded-2xl p-6 flex flex-col gap-6 opacity-60 
grayscale-[50%]">
<div class="flex justify-between items-center">
<div class="flex items-center gap-4">
<div class="w-14 h-14 rounded-2xl bg-white/5 border border-white/10 flex items-
center justify-center">
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


<span class="material-symbols-outlined text-white/40 text-3xl" data-
icon="gavel">gavel</span>
</div>
<div>
<h3 class="text-xl font-black text-white/60">S-03 异议处理(价格/竞品)</h3>
</div>
</div>
<span class="bg-white/5 text-white/40 px-3 py-1 rounded-full text-xs font-bold 
border border-white/10">未解锁</span>
</div>
<div class="grid grid-cols-1 md:grid-cols-2 gap-3 pointer-events-none">
<div class="sub-item rounded-xl p-3 flex items-center justify-between opacity-
50">
<span class="text-sm font-semibold">3.1 处理“太贵了”</span>
<span class="material-symbols-outlined text-white/40" data-icon="lock" 
style="font-size: 18px">lock</span>
</div>
<div class="sub-item rounded-xl p-3 flex items-center justify-between opacity-
50">
<span class="text-sm font-semibold">3.2 对比竞品话术</span>
<span class="material-symbols-outlined text-white/40" data-icon="lock" 
style="font-size: 18px">lock</span>
</div>
</div>
<p class="text-xs text-white/40 italic">完成 S-02 关卡后解锁此场景集</p>
</div>
<!-- S-04 Stage (Locked) -->
<div class="gamified-card rounded-2xl p-6 flex flex-col gap-6 opacity-60 
grayscale-[50%]">
<div class="flex justify-between items-center">
<div class="flex items-center gap-4">
<div class="w-14 h-14 rounded-2xl bg-white/5 border border-white/10 flex items-
center justify-center">
<span class="material-symbols-outlined text-white/40 text-3xl" data-
icon="meeting_room">meeting_room</span>
</div>
<div>
<h3 class="text-xl font-black text-white/60">S-04 进店访谈与成交</h3>
</div>
</div>
<span class="bg-white/5 text-white/40 px-3 py-1 rounded-full text-xs font-bold 
border border-white/10">未解锁</span>
</div>
<div class="grid grid-cols-1 md:grid-cols-2 gap-3 pointer-events-none">
<div class="sub-item rounded-xl p-3 flex items-center justify-between opacity-
50">
<span class="text-sm font-semibold">4.1 访谈关键人</span>
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
168
169


<span class="material-symbols-outlined text-white/40" data-icon="lock" 
style="font-size: 18px">lock</span>
</div>
<div class="sub-item rounded-xl p-3 flex items-center justify-between opacity-
50">
<span class="text-sm font-semibold">4.2 踢好临门一脚</span>
<span class="material-symbols-outlined text-white/40" data-icon="lock" 
style="font-size: 18px">lock</span>
</div>
</div>
<p class="text-xs text-white/40 italic">完成 S-03 关卡后解锁此场景集</p>
</div>
</div>