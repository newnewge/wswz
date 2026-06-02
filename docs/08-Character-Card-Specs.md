# 模块八：角色卡组件规范（Character Card Specs）

> 来源: 飞书文档「前端代码-松鼠ai培训助手前端界面」
> 模块: 角色卡组件规范 · Module 8/9

---

文件：character-card-specs.html · 亮色主题，角色卡交互规范
① Tailwind Config 色板配置
代码块
<script id="tailwind-config">
        tailwind.config = {
          darkMode: "class",
          theme: {
            extend: {
              "colors": {
                      "on-tertiary-fixed": "#002113",
                      "surface-bg": "#F8FAFC",
                      "on-primary-fixed-variant": "#003ab1",
                      "on-surface": "#111c2d",
                      "on-primary": "#ffffff",
                      "on-background": "#111c2d",
                      "surface-container-low": "#f0f3ff",
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


                      "surface-dim": "#cfdaf2",
                      "error-container": "#ffdad6",
                      "primary-fixed-dim": "#b6c4ff",
                      "tertiary-fixed": "#6ffbbe",
                      "parent-anxious": "#FF7A00",
                      "surface-variant": "#d8e3fb",
                      "secondary-fixed": "#ffdbc8",
                      "error": "#ba1a1a",
                      "secondary": "#994700",
                      "parent-observing": "#718096",
                      "failure-red": "#EF4444",
                      "outline": "#747686",
                      "inverse-surface": "#263143",
                      "secondary-container": "#fb7800",
                      "surface-bright": "#f9f9ff",
                      "inverse-on-surface": "#ecf1ff",
                      "surface-bright": "#f9f9ff",
                      "surface-container-high": "#dee8ff",
                      "surface-container-lowest": "#ffffff",
                      "on-secondary-fixed": "#321200",
                      "surface": "#f9f9ff",
                      "on-surface-variant": "#434654",
                      "surface-container": "#e7eeff",
                      "primary-container": "#1e52d9",
                      "tertiary-fixed-dim": "#4edea3",
                      "mascot-gold": "#FF9F1C",
                      "parent-rational": "#10B981",
                      "on-secondary": "#ffffff",
                      "on-primary-container": "#cfd7ff",
                      "primary-fixed": "#dce1ff",
                      "secondary-fixed-dim": "#ffb68b",
                      "on-secondary-fixed-variant": "#753400",
                      "on-tertiary-fixed-variant": "#005236",
                      "surface-tint": "#1d52d9",
                      "surface-container-highest": "#d8e3fb",
                      "on-tertiary-container": "#65f2b5",
                      "outline-variant": "#c4c5d7",
                      "tertiary-container": "#006d4a",
                      "on-error": "#ffffff",
                      "parent-confused": "#00B2FF",
                      "on-primary-fixed": "#00164f",
                      "primary": "#003bb2",
                      "tertiary": "#005237",
                      "on-tertiary": "#ffffff",
                      "background": "#f9f9ff",
                      "on-error-container": "#93000a",
                      "inverse-primary": "#b6c4ff",
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
55
56
57
58
59
60


                      "on-secondary-container": "#592600"
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
                      "gutter": "16px",
                      "container-margin": "24px",
                      "card-padding": "16px"
              },
              "fontFamily": {
                      "headline-md": ["Hanken Grotesk"],
                      "headline-lg": ["Hanken Grotesk"],
                      "label-caps": ["Inter"],
                      "body-base": ["Inter"]
              },
              "fontSize": {
                      "label-caps": ["12px", {"lineHeight": "16px", 
"letterSpacing": "0.05em", "fontWeight": "600"}],
                      "body-base": ["14px", {"lineHeight": "22px", 
"fontWeight": "400"}],
                      "headline-md": ["20px", {"lineHeight": "28px", 
"fontWeight": "600"}],
                      "headline-lg": ["32px", {"lineHeight": "40px", 
"fontWeight": "700"}]
              }
            }
          }
        }
    </script>
② Custom CSS 样式
代码块

        body { font-family: 'Inter', sans-serif; }
        .font-headline { font-family: 'Hanken Grotesk', sans-serif; }
        .material-symbols-outlined {
            font-variation-settings: 'FILL' 0, 'wght' 400, 'GRAD' 0, 'opsz' 24;
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
1
2
3
4
5


        }
        .card-flip-container {
            perspective: 1000px;
        }
        .card-inner {
            transition: transform 0.6s;
            transform-style: preserve-3d;
            position: relative;
        }
        .card-flip-container:hover .card-inner {
            transform: rotateY(180deg);
        }
        .card-front, .card-back {
            backface-visibility: hidden;
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
        .card-back {
            transform: rotateY(180deg);
        }
        .glass-panel {
            background: rgba(255, 255, 255, 0.05);
            backdrop-filter: blur(10px);
            border: 1px solid rgba(255, 255, 255, 0.1);
        }

③ Card Specs Body 规范主体
代码块
</nav>
<!-- Main Content -->
<main class="ml-64 min-h-screen flex flex-col">
<!-- TopAppBar -->
<header class="h-16 flex justify-between items-center px-gutter w-full bg-
[#001a4d] border-b-4 border-on-primary-fixed-variant shadow-md">
<div class="flex items-center gap-4">
<h1 class="font-headline-md text-headline-md font-bold text-on-primary">家长角色
库 - 标准化组件规范</h1>
<div class="flex items-center bg-white/10 rounded-full px-4 py-1.5 gap-2">
<span class="material-symbols-outlined text-white/60 text-sm">search</span>
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
1
2
3
4
5
6
7
8
9


<input class="bg-transparent border-none text-white text-sm focus:ring-0 w-48 
placeholder-white/40" placeholder="搜索家长角色..." type="text"/>
</div>
</div>
<div class="flex items-center gap-4">
<button class="text-on-primary hover:bg-primary-container/50 p-2 rounded-full 
transition-colors">
<span class="material-symbols-outlined">notifications</span>
</button>
<button class="text-on-primary hover:bg-primary-container/50 p-2 rounded-full 
transition-colors">
<span class="material-symbols-outlined">emoji_events</span>
</button>
<div class="w-10 h-10 rounded-full border-2 border-mascot-gold overflow-
hidden">
<img alt="Supervisor Profile" class="w-full h-full object-cover" 
src="https://lh3.googleusercontent.com/aida-public/AB6AXuA9OwEDL7o0dQHPKd32nf-
BLq4T7o5Yb2AqUEFnT_gbcfDA6HGJ2rO_22k9Z623ckFb1M4ehAiTguJ9091kLv5iydDw_za7EzOO_e
ky3jMKj6I8JBnP9q1UHwF5C96FPnJa2sqtKbd4s7sJBDjfxQBH8GjtUuPVCz_ivZO4ezd8p4BYtMhjL
ZduSMQikKq5ZawQMr5KOItXcO4FhhxjR2P3BqpFdkx8by-
geYkMENX8u6xascUwcks1BvgP2f100_GDfdaAP9ti4yyB"/>
</div>
</div>
</header>
<!-- Canvas Area -->
<section class="flex-grow p-8 overflow-y-auto"><div class="grid grid-cols-1 
md:grid-cols-2 xl:grid-cols-4 gap-gutter"><!-- P-01 Card --><div class="flex 
flex-col gap-4"><div class="bg-white rounded-3xl overflow-hidden shadow-lg p-6 
flex flex-col items-center text-center"><p class="text-[10px] font-bold text-
parent-anxious mb-2 uppercase tracking-widest">Front View</p><div class="w-24 
h-24 rounded-full border-4 border-parent-anxious mb-4 p-1"><img alt="P-01" 
class="w-full h-full rounded-full object-cover" 
src="https://lh3.googleusercontent.com/aida/ADBb0ujtodUvUVt7GCpiBPHexAlVMsXVh2_
BzsMy6fzL0dzijwzvFROCdl5orj-kQYAQhr_U34cFVtZjce3AbJfoqJh5NnIxA3d1MRrme-
6x3Re_PJkDQ0zmaf0M9nLuF9t-4wTiTYOsw2K7HRgAtGkvjuYiq0DxxsoqKNfNa7y-dc-
C1VMwdZCbp9uMz6nI-_f3pp-6QuGdcuqTgHzqXS0ACU4QDy_-
VI7IlKgYmQhT30vaqNhjUPYa7l3zgrs"/></div><h3 class="text-headline-md font-bold 
text-on-surface mb-1">张宝妈</h3><span class="bg-parent-anxious/10 text-parent-
anxious text-[11px] px-2 py-0.5 rounded-full font-bold mb-4">P-01 焦虑型</span>
<p class="text-body-base italic text-on-surface-variant leading-relaxed mb-
4">“隔壁王小明都报了三个班了，我家孩子再不学就真的废了，老师你得帮帮我！”</p><div 
class="flex flex-wrap justify-center gap-1"><span class="text-[10px] bg-
surface-container px-2 py-1 rounded text-outline">急于求成</span><span 
class="text-[10px] bg-surface-container px-2 py-1 rounded text-outline">高度敏感
</span></div></div><div class="bg-slate-900 rounded-3xl p-6 border-t-4 border-
parent-anxious shadow-xl text-white"><p class="text-[10px] font-bold text-
parent-anxious mb-3 uppercase tracking-widest">Back View (Strategy)</p><div 
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


class="space-y-4"><section><h4 class="text-label-caps text-white/50 mb-1">核心痛
点</h4><p class="text-body-base">极度担心被同龄人甩开，缺乏安全感，对微小退步零容忍。
</p></section><section><h4 class="text-label-caps text-white/50 mb-1">推荐技能
</h4><p class="text-body-base text-parent-anxious font-bold">SK-01 焦虑家长安抚
</p></section><section><h4 class="text-label-caps text-white/50 mb-1">实战策略
</h4><p class="text-body-base">通过展现阶段性量化成果来建立即时安全感，减少虚无对比。
</p></section></div></div></div><!-- P-02 Card --><div class="flex flex-col 
gap-4"><div class="bg-white rounded-3xl overflow-hidden shadow-lg p-6 flex 
flex-col items-center text-center"><p class="text-[10px] font-bold text-parent-
confused mb-2 uppercase tracking-widest">Front View</p><div class="w-24 h-24 
rounded-full border-4 border-parent-confused mb-4 p-1"><img alt="P-02" 
class="w-full h-full rounded-full object-cover" 
src="https://lh3.googleusercontent.com/aida/ADBb0uj4Dw06TxBvUxvOeXR50kTaTaEpo-
nqRKL9YTzEZHk0CrPNqHkFiDVDr4GFhvNRohci4Wn6mvJ00G8kHfYlDvjZFqpnUsQY33okMC7wkAMBm
kbmAbz5Ix8dNK7RlA06EPXFRa8Y9wApNhLbo3nGmLoxTnAZIYM9QFeQVNYUqoyfmfdU-5-
Y3f4NSfAu99y5sIS8eOxH3Kgwldr3Ox4dwhLRCa15zWvwm5RukvefcwiR0ZgzgshIMZQ3Ip1-"/>
</div><h3 class="text-headline-md font-bold text-on-surface mb-1">科技爸</h3>
<span class="bg-parent-confused/10 text-parent-confused text-[11px] px-2 py-
0.5 rounded-full font-bold mb-4">P-02 迷茫型</span><p class="text-body-base 
italic text-on-surface-variant leading-relaxed mb-4">“我也知道AI重要，但网上产品太
多了，我真看不出你们和免费的有什么区别。”</p><div class="flex flex-wrap justify-
center gap-1"><span class="text-[10px] bg-surface-container px-2 py-1 rounded 
text-outline">追求性价比</span><span class="text-[10px] bg-surface-container px-
2 py-1 rounded text-outline">选择困难</span></div></div><div class="bg-slate-
900 rounded-3xl p-6 border-t-4 border-parent-confused shadow-xl text-white"><p 
class="text-[10px] font-bold text-parent-confused mb-3 uppercase tracking-
widest">Back View (Strategy)</p><div class="space-y-4"><section><h4 
class="text-label-caps text-white/50 mb-1">核心痛点</h4><p class="text-body-
base">对前沿概念有基本了解但缺乏深度，容易被碎片化信息干扰。</p></section><section>
<h4 class="text-label-caps text-white/50 mb-1">推荐技能</h4><p class="text-body-
base text-parent-confused font-bold">SK-05 价值差异化呈现</p></section><section>
<h4 class="text-label-caps text-white/50 mb-1">实战策略</h4><p class="text-body-
base">将技术优势转化为具体的成长路径图，帮助其排除杂音。</p></section></div></div>
</div><!-- P-03 Card --><div class="flex flex-col gap-4"><div class="bg-white 
rounded-3xl overflow-hidden shadow-lg p-6 flex flex-col items-center text-
center"><p class="text-[10px] font-bold text-parent-rational mb-2 uppercase 
tracking-widest">Front View</p><div class="w-24 h-24 rounded-full border-4 
border-parent-rational mb-4 p-1"><img alt="P-03" class="w-full h-full rounded-
full object-cover" 
src="https://lh3.googleusercontent.com/aida/ADBb0uiuDNAXPsqNLuBn-98OREDzUBwLvK-
OEI9vHGSFkg4PIf_f9hKKtkD6Aj13pDsHfY3DTjtLDUN5sw1ae1PEM4GZCbW-
ngSBJabasxkAJ8CvikIKvsA4C8qGQhxZV_vSOkH75BYgtqkmcVdO_WSx_l5qAEhYjsOCtA8s3hrgGLJ
VcZR8imT8T11XSfeVv0XqlRaPQ2GxkmnzVxa91AQzQJi0eXYbhuJl3uzAVZLwq-qxDsOi6mvGx-
wgKSE"/></div><h3 class="text-headline-md font-bold text-on-surface mb-1">严父
</h3><span class="bg-parent-rational/10 text-parent-rational text-[11px] px-2 
py-0.5 rounded-full font-bold mb-4">P-03 理性型</span><p class="text-body-base 
italic text-on-surface-variant leading-relaxed mb-4">“不要跟我讲这些花里胡哨的。请


直接出示你们的量化评估体系和ROI回报数据。”</p><div class="flex flex-wrap justify-
center gap-1"><span class="text-[10px] bg-surface-container px-2 py-1 rounded 
text-outline">数据驱动</span><span class="text-[10px] bg-surface-container px-2 
py-1 rounded text-outline">逻辑严密</span></div></div><div class="bg-slate-900 
rounded-3xl p-6 border-t-4 border-parent-rational shadow-xl text-white"><p 
class="text-[10px] font-bold text-parent-rational mb-3 uppercase tracking-
widest">Back View (Strategy)</p><div class="space-y-4"><section><h4 
class="text-label-caps text-white/50 mb-1">核心痛点</h4><p class="text-body-
base">只相信逻辑、数据和权威背书，极其厌恶感性营销和空头承诺。</p></section><section>
<h4 class="text-label-caps text-white/50 mb-1">推荐技能</h4><p class="text-body-
base text-parent-rational font-bold">SK-09 逻辑架构说服</p></section><section>
<h4 class="text-label-caps text-white/50 mb-1">实战策略</h4><p class="text-body-
base">提供深度对比白皮书，用逻辑推演和历史数据模型进行闭环沟通。</p></section></div>
</div></div><!-- P-04 Card --><div class="flex flex-col gap-4"><div class="bg-
white rounded-3xl overflow-hidden shadow-lg p-6 flex flex-col items-center 
text-center"><p class="text-[10px] font-bold text-parent-observing mb-2 
uppercase tracking-widest">Front View</p><div class="w-24 h-24 rounded-full 
border-4 border-parent-observing mb-4 p-1"><img alt="P-04" class="w-full h-
full rounded-full object-cover" 
src="https://lh3.googleusercontent.com/aida/ADBb0ujCvWt9r7lUeRlvZKdHM9zqpBkstG0
eB_aEgOUElblDrLakBOUQVwpeQeX__RIYCrhLBZN9TrDbPuWSRJAeut_p0gc72file-
Me3aa0JDLIuGrlDbmu_B12d0hrz5poyssgV0ekf1BbvREjPnH3_afqU1seHwtH5DzduZQ7jroZax4qx
pwYfVhAEsd6R6LZoIOhR6sqcMfzQTmOtvIqHmZAxOPhVVZzVNIjgfaUByXOTFm_GmYyvP241zQ"/>
</div><h3 class="text-headline-md font-bold text-on-surface mb-1">优雅妈</h3>
<span class="bg-parent-observing/10 text-parent-observing text-[11px] px-2 py-
0.5 rounded-full font-bold mb-4">P-04 观望型</span><p class="text-body-base 
italic text-on-surface-variant leading-relaxed mb-4">“课程看起来挺好，但我想再对比
几家，顺便看看孩子自己的兴趣。”</p><div class="flex flex-wrap justify-center gap-
1"><span class="text-[10px] bg-surface-container px-2 py-1 rounded text-
outline">侧重体验</span><span class="text-[10px] bg-surface-container px-2 py-1 
rounded text-outline">低迫切感</span></div></div><div class="bg-slate-900 
rounded-3xl p-6 border-t-4 border-parent-observing shadow-xl text-white"><p 
class="text-[10px] font-bold text-parent-observing mb-3 uppercase tracking-
widest">Back View (Strategy)</p><div class="space-y-4"><section><h4 
class="text-label-caps text-white/50 mb-1">核心痛点</h4><p class="text-body-
base">注重品牌形象与孩子体验，不愿被销售压力裹挟，喜欢“软着陆”。</p></section>
<section><h4 class="text-label-caps text-white/50 mb-1">推荐技能</h4><p 
class="text-body-base text-parent-observing font-bold">SK-12 情感纽带建立</p>
</section><section><h4 class="text-label-caps text-white/50 mb-1">实战策略</h4>
<p class="text-body-base">邀请参与沉浸式开放日，让孩子自主反馈作为决策主导。</p>
</section></div></div></div></div></section>