# 模块七：团队训练看板（Team Dashboard）

> 来源: 飞书文档「前端代码-松鼠ai培训助手前端界面」
> 模块: 团队训练看板 · Module 7/9

---

文件：team-dashboard.html · 含数据看板和 KPI 可视化
① Tailwind Config 色板配置
代码块
<script id="tailwind-config">
        tailwind.config = {
            darkMode: "class",
            theme: {
                extend: {
                    "colors": {
                        "primary-fixed-dim": "#b6c4ff",
                        "secondary-fixed-dim": "#ffb68b",
                        "surface-variant": "#d8e3fb",
                        "on-primary-fixed-variant": "#003ab1",
                        "secondary-fixed": "#ffdbc8",
                        "on-secondary-fixed": "#321200",
                        "parent-confused": "#00B2FF",
                        "on-primary-fixed": "#00164f",
                        "surface-bg": "#F8FAFC",
                        "secondary": "#994700",
                        "on-tertiary-fixed": "#002113",
                        "inverse-primary": "#b6c4ff",
                        "on-secondary": "#ffffff",
                        "failure-red": "#EF4444",
                        "parent-observing": "#718096",
                        "surface-container-highest": "#d8e3fb",
                        "surface-container": "#e7eeff",
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


                        "background": "#00164f", // Deep Navy Override for 
Workspace
                        "on-error": "#ffffff",
                        "tertiary-fixed": "#6ffbbe",
                        "primary-container": "#1e52d9",
                        "parent-anxious": "#FF7A00",
                        "primary": "#003bb2",
                        "secondary-container": "#fb7800",
                        "mascot-gold": "#FF9F1C",
                        "error": "#ba1a1a",
                        "surface-tint": "#1d52d9",
                        "on-error-container": "#93000a",
                        "on-surface": "#111c2d",
                        "surface-container-low": "#f0f3ff",
                        "surface-bright": "#f9f9ff",
                        "on-primary": "#ffffff",
                        "on-background": "#ffffff",
                        "on-surface-variant": "#434654",
                        "inverse-surface": "#263143",
                        "surface": "#f9f9ff",
                        "parent-rational": "#10B981",
                        "tertiary": "#005237",
                        "on-secondary-fixed-variant": "#753400",
                        "primary-fixed": "#dce1ff",
                        "outline": "#747686",
                        "surface-dim": "#cfdaf2",
                        "outline-variant": "#c4c5d7",
                        "tertiary-container": "#006d4a",
                        "on-tertiary": "#ffffff",
                        "surface-container-lowest": "#ffffff",
                        "on-primary-container": "#cfd7ff",
                        "error-container": "#ffdad6",
                        "on-tertiary-fixed-variant": "#005236",
                        "on-tertiary-container": "#65f2b5",
                        "tertiary-fixed-dim": "#4edea3",
                        "inverse-on-surface": "#ecf1ff",
                        "on-secondary-container": "#592600"
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
66
67
68
69


                        "stack-md": "16px",
                        "card-padding": "16px",
                        "stack-sm": "8px",
                        "unit": "8px",
                        "gutter": "16px",
                        "container-margin": "24px"
                    },
                    "fontFamily": {
                        "body-base": ["Inter"],
                        "label-caps": ["Inter"],
                        "headline-lg": ["Hanken Grotesk"],
                        "headline-md": ["Hanken Grotesk"]
                    },
                    "fontSize": {
                        "body-base": ["14px", {"lineHeight": "22px", 
"fontWeight": "400"}],
                        "label-caps": ["12px", {"lineHeight": "16px", 
"letterSpacing": "0.05em", "fontWeight": "600"}],
                        "headline-lg": ["32px", {"lineHeight": "40px", 
"fontWeight": "900"}],
                        "headline-md": ["20px", {"lineHeight": "28px", 
"fontWeight": "700"}]
                    }
                },
            },
        }
    </script>
② Custom CSS 样式
代码块

        .material-symbols-outlined {
            font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 48;
        }
        .gamified-card {
            border-bottom-width: 6px;
            transition: all 0.2s ease;
        }
        .gamified-card:active {
            transform: translateY(4px);
            border-bottom-width: 2px;
        }
        .custom-scrollbar::-webkit-scrollbar {
            width: 6px;
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


        }
        .custom-scrollbar::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.05);
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background: rgba(255, 255, 255, 0.2);
            border-radius: 10px;
        }

③ Dashboard Body 看板主体
代码块
</nav>
<button class="mt-4 bg-white text-secondary font-bold py-3 rounded-2xl border-
b-4 border-secondary/20 active:border-b-0 active:translate-y-[2px] transition-
all">
            开始新训练
        </button>
<div class="mt-auto border-t border-secondary/20 pt-4 flex flex-col gap-2">
<a class="flex items-center gap-3 px-4 py-2 text-on-secondary-container/80 
hover:bg-secondary/10 rounded-xl transition-colors" href="#">
<span class="material-symbols-outlined">settings</span>
<span class="font-body-base text-body-base">设置</span>
</a>
<a class="flex items-center gap-3 px-4 py-2 text-on-secondary-container/80 
hover:bg-secondary/10 rounded-xl transition-colors" href="#">
<span class="material-symbols-outlined">logout</span>
<span class="font-body-base text-body-base">退出</span>
</a>
</div>
</aside>
<!-- Main Workspace -->
<main class="ml-64 flex-grow h-screen flex flex-col">
<!-- TopAppBar Component -->
<header class="h-16 flex justify-between items-center px-gutter w-full bg-
primary-container border-b-4 border-on-primary-fixed-variant shadow-md z-40">
<div class="flex items-center gap-6">
<h2 class="font-headline-md text-headline-md font-bold text-on-primary">团队对练
数据看板</h2>
<div class="flex bg-white/10 rounded-xl p-1 gap-1">
<button class="px-4 py-1 text-on-primary bg-white/20 rounded-lg text-label-
caps">本周</button>
<button class="px-4 py-1 text-on-primary/60 hover:text-on-primary transition-
colors text-label-caps">本月</button>
15
16
17
18
19
20
21
22
23
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


<div class="h-6 w-[1px] bg-white/20 mx-1 self-center"></div>
<button class="flex items-center gap-2 px-4 py-1 text-on-primary/60 hover:text-
on-primary transition-colors text-label-caps">
<span class="material-symbols-outlined text-[16px]">calendar_month</span>
<span>05/15 - 05/22</span>
</button>
</div>
</div>
<div class="flex items-center gap-4">
<button class="flex items-center gap-2 bg-mascot-gold text-white font-bold px-
4 py-2 rounded-xl border-b-4 border-secondary/40 active:border-b-0 
active:translate-y-[2px] transition-all">
<span class="material-symbols-outlined">download</span>
<span class="font-label-caps">导出报告</span>
</button>
<div class="flex items-center gap-2">
<span class="material-symbols-outlined text-on-primary hover:bg-white/10 p-2 
rounded-full cursor-pointer">notifications</span>
<span class="material-symbols-outlined text-on-primary hover:bg-white/10 p-2 
rounded-full cursor-pointer">emoji_events</span>
<div class="w-10 h-10 rounded-full border-2 border-on-primary overflow-hidden 
shadow-sm">
<img alt="Supervisor Profile" class="w-full h-full object-cover" 
src="https://lh3.googleusercontent.com/aida-public/AB6AXuAGNNIhP0TIR5DLvsP-
GX8UcEWV7U_YQILjOdq33iicHYvfMWqOxh_lIu2xXp3yGy5IUiH3_bPq5-
AprGHkH16y0OREvIz_1RWV_CB-9EP0WuATASTGKqdlsGCp5305XaQbUf_UZusk-
f2zLflEhsDb9npCONghaJfNkz_ZqaOanx6cOq0Abf_GOZHhhPUWKQ7inLqoZVoWKpCjNhF7yjDEvp8P
SaSKNwe5TnMyUICwxaSRidt8bbgUrpqYBPRfOYw3JXSLTKvuAAg4">
</div>
</div>
</div>
</header>
<!-- Scrollable Dashboard Content -->
<div class="flex-grow overflow-y-auto custom-scrollbar p-gutter space-y-gutter 
pb-20">
<!-- Statistics Row -->
<div class="grid grid-cols-1 md:grid-cols-3 gap-gutter">
<!-- Avg Score -->
<div class="gamified-card bg-surface-container-lowest p-card-padding rounded-
3xl border-b-4 border-surface-variant flex items-center justify-between shadow-
sm">
<div class="space-y-1">
<p class="text-on-surface-variant font-label-caps uppercase tracking-wider">团队
平均分</p>
<div class="flex items-baseline gap-2">
<span class="font-headline-lg text-headline-lg text-on-surface">88.5</span>
<span class="text-parent-rational font-bold">+2.4 ↑</span>
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


</div>
</div>
<div class="w-16 h-16 bg-mascot-gold/10 rounded-2xl flex items-center justify-
center border-2 border-mascot-gold/20">
<span class="material-symbols-outlined text-[40px] text-mascot-gold" 
style="font-variation-settings: 'FILL' 1;">emoji_events</span>
</div>
</div>
<!-- Activity -->
<div class="gamified-card bg-surface-container-lowest p-card-padding rounded-
3xl border-b-4 border-surface-variant flex items-center justify-between shadow-
sm">
<div class="space-y-1">
<p class="text-on-surface-variant font-label-caps uppercase tracking-wider">训练
活跃度</p>
<div class="flex items-baseline gap-2">
<span class="font-headline-lg text-headline-lg text-on-surface">92%</span>
<span class="text-parent-rational font-bold">全员参与</span>
</div>
</div>
<div class="w-16 h-16 bg-parent-anxious/10 rounded-2xl flex items-center 
justify-center border-2 border-parent-anxious/20">
<span class="material-symbols-outlined text-[40px] text-parent-anxious" 
style="font-variation-settings: 'FILL' 1;">local_fire_department</span>
</div>
</div>
<!-- Pass Rate -->
<div class="gamified-card bg-surface-container-lowest p-card-padding rounded-
3xl border-b-4 border-surface-variant flex items-center justify-between shadow-
sm">
<div class="space-y-1">
<p class="text-on-surface-variant font-label-caps uppercase tracking-wider">通关
率 (Lv.3+)</p>
<div class="flex items-baseline gap-2">
<span class="font-headline-lg text-headline-lg text-on-surface">75%</span>
<span class="text-on-surface-variant font-body-base">6/8 成员</span>
</div>
</div>
<div class="w-16 h-16 bg-parent-rational/10 rounded-2xl flex items-center 
justify-center border-2 border-parent-rational/20">
<span class="material-symbols-outlined text-[40px] text-parent-rational" 
style="font-variation-settings: 'FILL' 1;">check_circle</span>
</div>
</div>
</div>
<!-- Heatmap Section -->
<div class="grid grid-cols-1 lg:grid-cols-4 gap-gutter">
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


<div class="lg:col-span-3 gamified-card bg-surface-container-lowest p-6 
rounded-3xl border-b-4 border-surface-variant shadow-sm">
<div class="flex justify-between items-center mb-6">
<h3 class="font-headline-md text-headline-md text-on-surface flex items-center 
gap-2">
<span class="material-symbols-outlined text-primary">analytics</span>
                            核心技能掌握度
                        </h3>
<div class="flex items-center gap-4 text-label-caps text-on-surface-variant">
<div class="flex items-center gap-1"><div class="w-3 h-3 bg-primary-fixed-dim 
rounded"></div> 低</div>
<div class="flex items-center gap-1"><div class="w-3 h-3 bg-primary-container 
rounded"></div> 中</div>
<div class="flex items-center gap-1"><div class="w-3 h-3 bg-primary rounded">
</div> 高</div>
</div>
</div>
<div class="overflow-x-auto">
<table class="w-full text-left">
<thead>
<tr class="text-label-caps text-on-surface-variant">
<th class="py-2 pr-4">成员</th>
<th class="py-2 px-1 text-center">SK-01<br>焦虑安抚</th>
<th class="py-2 px-1 text-center">SK-02<br>需求挖掘</th>
<th class="py-2 px-1 text-center">SK-03<br>竞品对比</th>
<th class="py-2 px-1 text-center">SK-04<br>价值传递</th>
<th class="py-2 px-1 text-center">SK-05<br>价格异议</th>
<th class="py-2 px-1 text-center">SK-06<br>成交促成</th>
</tr>
</thead>
<tbody class="text-body-base">
<script>
                                    const members = ["张伟 (S)", "李娜 (S)", "王
强 (S)", "赵敏 (S)", "刘杰 (J)", "陈芳 (J)", "周涛 (J)", "徐平 (J)"];
                                    const skillLevels = [
                                        [90, 85, 95, 88, 65, 80],
                                        [88, 92, 85, 90, 70, 85],
                                        [95, 90, 92, 85, 60, 92],
                                        [82, 88, 80, 92, 55, 78],
                                        [65, 70, 60, 55, 40, 50],
                                        [70, 65, 55, 68, 45, 60],
                                        [60, 75, 50, 62, 35, 55],
                                        [55, 60, 45, 50, 30, 45]
                                    ];

                                    document.write(members.map((name, i) => `  
                                      <tr class="border-t border-surface-
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


container-low">                                             <td class="py-3 pr-
4 font-bold text-on-surface">${name}</td>                                      
       ${skillLevels[i].map(score => {                                         
        let bgColor = 'bg-primary-fixed-dim';                                  
               if(score > 80) bgColor = 'bg-primary';                          
                       else if(score > 60) bgColor = 'bg-primary-container';   
                                              return`<td class="p-1">
                                                    <div class="h-10 w-full 
<equation>{bgColor} rounded-lg flex items-center justify-center text-white 
font-bold text-[10px] shadow-inner opacity-90 hover:opacity-100 transition-
opacity cursor-pointer">
                                                        </equation>{score}
                                                    </div>
                                                </td>`;                        
                     }).join('')}                                         
</tr>                                     `).join(''));
                                </script>
</tbody>
</table>
</div>
</div>
<!-- AI Mentor Insights -->
<div class="lg:col-span-1 flex flex-col gap-gutter">
<div class="gamified-card bg-surface-container-lowest p-6 rounded-3xl border-b-
4 border-mascot-gold shadow-sm flex flex-col items-center relative h-full">
<div class="absolute -top-10 left-1/2 -translate-x-1/2 w-24 h-24">
<img alt="Master Liu" class="w-full h-full drop-shadow-xl" 
src="https://lh3.googleusercontent.com/aida/ADBb0uj8TuiAgS9y8yo4zD_Azu8mnDVCkdc
5ENHhK3-AQCNuRIPn4SrCXdG8nr53RTBA_OC_EDCl79Od7-d5OMgEAvMp2TQcygsx2XESub-
sRsHMFbB-
bbSYHyYbCnZPG9XdRi_1dcQSrNR3xbokzfjqo0SApaLCHGXXWRotPME_hvAAvFDnxYW7WLDpQ_tspPL
06PFxAL-n8y0rRhRX6mYAWwi-KSNLFgDeZmjTCOQbFFNYfaREBKusZoMhJKc">
</div>
<div class="mt-14 text-center space-y-4">
<h4 class="font-headline-md text-headline-md text-on-surface">刘老师全局诊断</h4>
<div class="bg-surface-container p-4 rounded-2xl relative border-2 border-
surface-variant">
<p class="text-body-base text-on-surface-variant leading-relaxed">
                                    "督导您好！分析完本周数据，我发现<span 
class="text-secondary font-bold">价格异议处理(SK-05)</span>是全队的共同薄弱点，初级
成员平均分仅为42分。建议安排一次专题对练会议。"
                                </p>
<div class="absolute -top-3 left-1/2 -translate-x-1/2 w-0 h-0 border-l-[10px] 
border-l-transparent border-r-[10px] border-r-transparent border-b-[10px] 
border-b-surface-container"></div>
</div>
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


<button class="w-full bg-primary text-white font-bold py-3 rounded-2xl border-
b-4 border-on-primary-fixed-variant hover:scale-105 active:scale-95 transition-
all">
                                发起专题挑战
                            </button>
</div>
</div>
</div>
</div>
<!-- Members Progress Table -->
<div class="gamified-card bg-surface-container-lowest p-6 rounded-3xl border-b-
4 border-surface-variant shadow-sm overflow-hidden">
<div class="flex justify-between items-center mb-6">
<h3 class="font-headline-md text-headline-md text-on-surface flex items-center 
gap-2">
<span class="material-symbols-outlined text-secondary-
container">trending_up</span>
                        成员进度追踪
                    </h3>
<div class="flex gap-2">
<span class="bg-primary/10 text-primary px-3 py-1 rounded-full text-label-
caps">资深销售 (4)</span>
<span class="bg-secondary/10 text-secondary px-3 py-1 rounded-full text-label-
caps">初级销售 (4)</span>
</div>
</div>
<div class="overflow-x-auto">
<table class="w-full text-left">
<thead>
<tr class="text-label-caps text-on-surface-variant border-b border-surface-
container">
<th class="py-3 px-4">成员信息</th>
<th class="py-3 px-4">当前等级</th>
<th class="py-3 px-4 text-center">训练场次</th>
<th class="py-3 px-4 text-center">平均分</th>
<th class="py-3 px-4">成功亮点 / 待提升</th>
</tr>
</thead>
<tbody class="text-body-base">
<script>
                                const memberRows = [
                                    { name: "张伟", role: "资深", lv: "Lv.5 专
家", count: 28, score: 95, highlight: "SK-03 竞品对比", improve: "SK-05 话术精
简", color: "bg-primary" },
                                    { name: "李娜", role: "资深", lv: "Lv.4 熟
练", count: 24, score: 88, highlight: "SK-01 沟通亲和", improve: "SK-06 成交迫切
性", color: "bg-primary" },
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


                                    { name: "刘杰", role: "初级", lv: "Lv.2 新
手", count: 42, score: 65, highlight: "SK-02 基础问答", improve: "SK-05 异议抗
压", color: "bg-secondary-container" },
                                    { name: "陈芳", role: "初级", lv: "Lv.1 见
习", count: 35, score: 58, highlight: "话术记忆力", improve: "SK-03 竞品库熟悉", 
color: "bg-secondary-container" }
                                ];

                                document.write(memberRows.map((m, i) => `      
                              <tr class="hover:bg-surface-container-low 
transition-colors group">                                         <td 
class="py-4 px-4 flex items-center gap-3">                                     
        <div class="w-10 h-10 rounded-full border-2 border-surface-variant 
overflow-hidden bg-white">                                                 
<img src="https://api.dicebear.com/7.x/bottts/svg?seed=member${i}" 
alt="${m.name}" class="w-full h-full">                                         
    </div>                                             <div>                   
                              <p class="font-bold text-on-surface">${m.name}
</p>                                                 <p class="text-label-caps 
text-on-surface-variant">${m.role}</p>                                         
    </div>                                         </td>                       
                  <td class="py-4 px-4">                                       
      <span class="${m.color} text-white px-3 py-1 rounded-full text-label-
caps shadow-sm">                                                 ${m.lv}       
                                      </span>                                  
       </td>                                         <td class="py-4 px-4 text-
center font-bold text-on-surface-variant">${m.count} 次</td>                   
                      <td class="py-4 px-4 text-center">                       
                      <span class="text-headline-md font-bold ${m.score > 80 ? 
'text-parent-rational' : 'text-parent-anxious'}">${m.score}</span>             
                            </td>                                         <td 
class="py-4 px-4">                                             <div 
class="flex flex-col gap-1">                                                 
<div class="flex items-center gap-1 text-[12px] text-parent-rational">         
                                            <span class="material-symbols-
outlined text-[14px]">check_circle</span>                                      
               ${m.highlight}                                                 
</div>                                                 <div class="flex items-
center gap-1 text-[12px] text-failure-red">                                    
                 <span class="material-symbols-outlined text-
[14px]">warning</span>                                                     
${m.improve}                                                 </div>            
                                 </div>                                        
 </td>                                     </tr>                               
 `).join(''));
                            </script>
</tbody>
190
191
192
193
194
195
196


</table>
</div>
</div>
</div>
<!-- Sticky Coach Drawer Notification (Mobile-friendly concept) -->
<div class="fixed bottom-6 right-6 z-50">
<button class="w-16 h-16 bg-mascot-gold rounded-full shadow-2xl flex items-
center justify-center border-4 border-white animate-bounce group relative">
<span class="material-symbols-outlined text-white text-
[32px]">psychology</span>
<div class="absolute -top-1 -right-1 w-6 h-6 bg-red-500 rounded-full border-2 
border-white text-white text-[10px] flex items-center justify-center font-
bold">2</div>
<!-- Tooltip -->
<div class="absolute bottom-full right-0 mb-4 w-48 scale-0 group-hover:scale-
100 transition-transform origin-bottom-right">
<div class="bg-white p-3 rounded-2xl shadow-xl border-2 border-mascot-gold 
text-secondary text-label-caps text-center">
                        刘老师有新建议哦！
                    </div>
</div>
</button>
</div>