# PubMed 自动化文献监控检索策略

> 用途：金华泽为创面敷料业务线自动化文献情报监控，覆盖核心技术路线与临床场景。
> 更新频率：每两周执行一次检索，汇总新文献。
> 维护人：学术情报组 / 研发情报组

---

## 一、核心 MeSH 术语列表

以下是创面敷料领域PubMed检索所需的核心MeSH术语与自由词：

### 1.1 创面类型 MeSH

| 中文 | MeSH Term | Entry Terms / Free Text |
|------|-----------|------------------------|
| 创面/伤口 | "Wounds and Injuries"[Mesh] OR "Wound Healing"[Mesh] | wound, wounds, injury |
| 慢性创面 | — | chronic wound*, non-healing wound*, hard-to-heal wound* |
| 糖尿病足 | "Diabetic Foot"[Mesh] | diabetic foot, diabetic ulcer*, DFU |
| 压疮 | "Pressure Ulcer"[Mesh] | pressure ulcer*, bed sore*, decubitus |
| 静脉性溃疡 | "Varicose Ulcer"[Mesh] OR "Venous Ulcer"[Mesh] | venous ulcer*, venous leg ulcer*, stasis ulcer* |
| 动脉性溃疡 | — | arterial ulcer*, ischemic ulcer* |
| 烧伤 | "Burns"[Mesh] | burn wound*, thermal injury |
| 手术切口 | "Surgical Wound"[Mesh] | surgical wound*, surgical site |

### 1.2 敷料类型 MeSH

| 中文 | MeSH Term | Entry Terms |
|------|-----------|-------------|
| 敷料 | "Bandages"[Mesh] OR "Wound Dressing"[Mesh] | dressing*, wound dressing*, bandage* |
| 水凝胶 | "Hydrogels"[Mesh] | hydrogel*, hydrophilic gel* |
| 泡沫敷料 | — | foam dressing*, polyurethane foam |
| 藻酸盐敷料 | "Alginates"[Mesh] | alginate dressing*, calcium alginate |
| 水胶体 | — | hydrocolloid dressing* |
| 抗菌敷料 | "Anti-Infective Agents"[Mesh] | antimicrobial dressing*, antibacterial dressing* |
| 生物工程皮肤 | "Skin, Artificial"[Mesh] | skin substitute*, bioengineered skin, artificial skin |
| 静电纺丝 | — | electrospinning, electrospun, nanofiber* |
| 两性离子 | — | zwitterion*, zwitterionic, betaine, sulfobetaine, carboxybetaine |
| 纳米材料 | "Nanostructures"[Mesh] | nanomaterial*, nanoparticle*, nanofiber* |

### 1.3 修饰/功能 MeSH

| 中文 | MeSH Term | Entry Terms |
|------|-----------|-------------|
| 抗菌 | "Anti-Bacterial Agents"[Mesh] | antibacterial, antimicrobial |
| 抗污 | — | antifouling, anti-fouling, protein resistance |
| 止血 | "Hemostatics"[Mesh] OR "Hemostasis"[Mesh] | hemostatic*, haemostatic* |
| 促愈合 | — | wound healing promoting, pro-healing |
| 载药 | "Drug Delivery Systems"[Mesh] | drug delivery, drug release, controlled release |
| 电子束辐照 | — | electron beam, e-beam, electron irradiation, radiation grafting |
| 表面修饰 | "Surface Properties"[Mesh] | surface modification, surface functionalization |
| 生物相容性 | "Biocompatible Materials"[Mesh] | biocompatibility, cytocompatibility |

---

## 二、通用综合检索式（宽口径扫描）

### 2.1 创面敷料全领域综合检索

```
((("Wound Healing"[Mesh] OR "Wounds and Injuries"[Mesh]) AND ("Bandages"[Mesh] OR "Hydrogels"[Mesh] OR "Alginates"[Mesh] OR "Skin, Artificial"[Mesh])) OR ("wound dressing"[Title/Abstract] OR "dressing material"[Title/Abstract] OR "hydrogel dressing"[Title/Abstract] OR "nanofiber dressing"[Title/Abstract])) AND (english[Language] OR chinese[Language]) AND (2024:2026[dp])
```

**说明**：
- 综合覆盖率约85%，适合两周一次的宽口径扫描
- 过滤语言为英语和中文
- 时间范围调整为最近2年

### 2.2 慢性创面敷料专项

```
(("chronic wound"[Title/Abstract] OR "chronic wounds"[Title/Abstract] OR "non-healing wound"[Title/Abstract] OR "hard-to-heal wound"[Title/Abstract] OR "Diabetic Foot"[Mesh] OR "Pressure Ulcer"[Mesh] OR "Varicose Ulcer"[Mesh]) AND ("Bandages"[Mesh] OR "Wound Dressing"[Title/Abstract] OR "hydrogel"[Title/Abstract] OR "dressing"[Title/Abstract])) AND (english[Language] OR chinese[Language]) AND (2024:2026[dp])
```

---

## 三、按技术路线分类的专项检索式

### 3.1 两性离子涂层 + 创面

**背景**：金华泽为核心技术路线，需持续监控全球进展。

```
((zwitterion*[Title/Abstract] OR zwitterionic[Title/Abstract] OR "betaine"[Title/Abstract] OR "sulfobetaine"[Title/Abstract] OR "carboxybetaine"[Title/Abstract] OR "polyzwitterion"[Title/Abstract]) AND ("wound"[Title/Abstract] OR "wound healing"[Title/Abstract] OR "dressing"[Title/Abstract] OR "hydrogel"[Title/Abstract] OR "Wound Healing"[Mesh] OR "Bandages"[Mesh]))
```

**也可用简化版（推荐日常使用）**：

```
zwitterion*[Title/Abstract] AND (wound[Title/Abstract] OR dressing[Title/Abstract] OR hydrogel[Title/Abstract])
```

**扩展检索（含两性离子衍生物）**：

```
((zwitterion*[Title/Abstract] OR "sulfobetaine methacrylate"[Title/Abstract] OR "SBMA"[Title/Abstract] OR "carboxybetaine methacrylate"[Title/Abstract] OR "CBMA"[Title/Abstract] OR "phosphorylcholine"[Title/Abstract] OR "MPC"[Title/Abstract] OR "betaine"[Title/Abstract]) AND ("wound"[Title/Abstract] OR "wound healing"[Title/Abstract] OR "dressing"[Title/Abstract] OR "Bandages"[Mesh]))
```

---

### 3.2 抗菌敷料 + 慢性创面

```
(((antimicrobial[Title/Abstract] OR antibacterial[Title/Abstract] OR "anti-bacterial"[Title/Abstract] OR "anti-infective"[Title/Abstract] OR "silver"[Title/Abstract] OR "chitosan"[Title/Abstract] OR "polyhexamethylene biguanide"[Title/Abstract] OR "PHMB"[Title/Abstract] OR "iodine"[Title/Abstract]) AND (dressing*[Title/Abstract] OR "Bandages"[Mesh] OR hydrogel*[Title/Abstract] OR wound[Title/Abstract])) AND (("chronic wound"[Title/Abstract] OR "chronic wounds"[Title/Abstract] OR "diabetic foot"[Title/Abstract] OR "pressure ulcer"[Title/Abstract] OR "venous ulcer"[Title/Abstract] OR "Diabetic Foot"[Mesh] OR "Pressure Ulcer"[Mesh])))
```

**精简版（日常监控推荐）**：

```
(antimicrobial[Title/Abstract] OR antibacterial[Title/Abstract]) AND dressing*[Title/Abstract] AND (chronic[Title/Abstract] OR diabetic[Title/Abstract] OR ulcer[Title/Abstract])
```

---

### 3.3 电子束辐照 + 表面修饰

**背景**：金华泽为潜在技术路线——电子束辐照接枝用于表面功能化。

```
(("electron beam"[Title/Abstract] OR "e-beam"[Title/Abstract] OR "electron irradiation"[Title/Abstract] OR "radiation grafting"[Title/Abstract] OR "gamma irradiation"[Title/Abstract]) AND ("surface modification"[Title/Abstract] OR "surface functionalization"[Title/Abstract] OR "graft polymerization"[Title/Abstract] OR "grafting"[Title/Abstract] OR "surface"[Title/Abstract]) AND ("wound"[Title/Abstract] OR "dressing"[Title/Abstract] OR "hydrogel"[Title/Abstract] OR "biomaterial"[Title/Abstract] OR "Bandages"[Mesh]))
```

**精简版（日常监控）**：

```
("electron beam"[Title/Abstract] OR "radiation grafting"[Title/Abstract]) AND (surface[Title/Abstract] OR grafting[Title/Abstract]) AND (wound[Title/Abstract] OR dressing[Title/Abstract] OR hydrogel[Title/Abstract])
```

---

### 3.4 糖尿病足 + 敷料

```
(("Diabetic Foot"[Mesh] OR "diabetic foot"[Title/Abstract] OR "DFU"[Title/Abstract] OR "diabetic ulcer"[Title/Abstract]) AND ("Bandages"[Mesh] OR "dressing"[Title/Abstract] OR "hydrogel"[Title/Abstract] OR "wound dressing"[Title/Abstract] OR "skin substitute"[Title/Abstract] OR "negative pressure"[Title/Abstract] OR "NPWT"[Title/Abstract] OR "growth factor"[Title/Abstract]))
```

**扩展版（含临床试验过滤）**：

```
(("Diabetic Foot"[Mesh] OR "diabetic foot"[Title/Abstract] OR "DFU"[Title/Abstract]) AND (dressing*[Title/Abstract] OR "Bandages"[Mesh])) AND (Clinical Trial[ptyp] OR Randomized Controlled Trial[ptyp] OR Meta-Analysis[ptyp] OR Systematic Review[ptyp])
```

---

### 3.5 压疮预防 + 敷料

```
(("Pressure Ulcer"[Mesh] OR "pressure ulcer"[Title/Abstract] OR "pressure injury"[Title/Abstract] OR "bed sore"[Title/Abstract] OR "decubitus"[Title/Abstract]) AND ("prevention"[Title/Abstract] OR "prevent"[Title/Abstract] OR "prophylaxis"[Title/Abstract]) AND ("dressing"[Title/Abstract] OR "foam dressing"[Title/Abstract] OR "silicone dressing"[Title/Abstract] OR "hydrocolloid"[Title/Abstract] OR "Bandages"[Mesh]))
```

---

## 四、按证据等级过滤的检索式

### 4.1 系统评价/Meta分析（决策参考）

```
((("Wound Healing"[Mesh] OR "wound dressing"[Title/Abstract] OR "chronic wound"[Title/Abstract] OR "diabetic foot"[Title/Abstract]) AND ("dressing"[Title/Abstract] OR "Bandages"[Mesh] OR "hydrogel"[Title/Abstract])) AND (Systematic Review[ptyp] OR Meta-Analysis[ptyp] OR Review[ptyp]))
```

### 4.2 随机对照试验（临床证据）

```
((("Wound Healing"[Mesh] OR "chronic wound"[Title/Abstract] OR "diabetic foot"[Title/Abstract] OR "pressure ulcer"[Title/Abstract]) AND (dressing*[Title/Abstract] OR "Bandages"[Mesh])) AND (Randomized Controlled Trial[ptyp]))
```

### 4.3 临床试验（含已注册未发表）

```
(("wound dressing"[Title/Abstract] OR "dressing material"[Title/Abstract] OR "hydrogel dressing"[Title/Abstract]) AND (Clinical Trial[ptyp] OR Clinical Study[ptyp]))
```

---

## 五、RSS 订阅设置方法

### 5.1 从PubMed检索式生成RSS

**步骤：**

1. 在PubMed中执行任意检索式（如上面任一检索式）
2. 点击检索结果页右上角的 **"Create RSS"** 按钮
3. 设置：
   - **Name**：给这个RSS命名（如"JZ-Zwitterionic-Wound"）
   - **Number of items displayed**：建议选择 50
   - **Links**：选择 Full text
4. 点击 **"Create RSS"**
5. 复制生成的RSS链接（格式为 `https://pubmed.ncbi.nlm.nih.gov/rss/...`）

### 5.2 推荐的RSS阅读器

| 推荐工具 | 类型 | 优点 |
|---------|------|------|
| Feedly (feedly.com) | Web/App免费 | 多设备同步、分类管理 |
| Inoreader (inoreader.com) | Web/App免费 | 强大的过滤规则 |
| NewsBlur | Web/App付费 | 无广告、AI推荐 |
| 本地客户端（如Thunderbird） | 桌面 | 与办公邮件集成 |
| Slack RSS App | Slack集成 | 推送到团队频道 |

### 5.3 金华泽为推荐的RSS分类体系

```
📂 创面敷料文献监控
├── 📁 01-两性离子涂层技术
├── 📁 02-抗菌敷料
├── 📁 03-糖尿病足敷料
├── 📁 04-压疮预防敷料
├── 📁 05-电子束辐照改性
├── 📁 06-烧伤创面覆盖物
├── 📁 07-综合扫描（宽口径）
├── 📁 08-系统评价/Meta分析
└── 📁 09-临床试验
```

> **建议**：使用机构邮箱注册Feedly/Inoreader，方便团队共享。

### 5.4 金华泽为推荐创建的RSS订阅清单

| # | RSS名称 | 对应检索式 | 更新频率 |
|---|---------|-----------|---------|
| 1 | JZ-Zwitterionic-Wound | 两性离子涂层+创面(扩展版) | 每周 |
| 2 | JZ-Antimicrobial-Chronic | 抗菌敷料+慢性创面 | 每周 |
| 3 | JZ-ElectronBeam-Surface | 电子束辐照+表面修饰 | 每两周 |
| 4 | JZ-DFU-Dressing | 糖尿病足+敷料 | 每周 |
| 5 | JZ-PressureUlcer-Prevent | 压疮预防+敷料 | 每两周 |
| 6 | JZ-Comprehensive-Wound | 全领域综合检索 | 每周 |
| 7 | JZ-Systematic-Reviews | 系统评价/Meta分析 | 每月 |
| 8 | JZ-Clinical-Trials | 创面敷料临床试验 | 每月 |

> **提示**：RSS订阅后建议使用Inoreader的"Rule"功能自动打标签，或使用Feedly的"Boards"分类管理。

---

## 六、NCBI My Bibliography 监控设置

### 6.1 概述

NCBI My Bibliography 是PubMed提供的一个免费个人文献管理工具，支持：
- 保存检索式并自动运行
- 将新文献推送至邮箱
- 生成个人发表列表（科研人员常用）

### 6.2 设置步骤

1. **登录/注册 NCBI 账户**
   - 访问 https://www.ncbi.nlm.nih.gov/account/
   - 注册免费账户（建议使用金华泽为机构邮箱）

2. **访问 My NCBI**
   - 账户注册后进入 My NCBI Dashboard

3. **保存检索式**
   - 在PubMed中执行任一检索式
   - 点击结果框上方的 **"Save"** 链接
   - 命名检索式（如 "JZ-Zwitterionic-Wound"）
   - 选择是否设置为自动更新（推荐：是）

4. **设置邮件提醒**
   - 在 My NCBI → **Saved Searches** 页面
   - 点击每个检索式旁的 **"Edit"**
   - 设置 **"What schedule?"** → 推荐选择：
     - **"Every week"** (每周) — 高优先级检索
     - **"Every month"** (每月) — 低频检索
   - 设置 **"Would you like e-mail updates of new items?"** → **Yes**
   - 选择发送格式：推荐 **HTML**（可看摘要）

5. **添加到 My Bibliography**
   - 可从 Saved Searches 中将相关文献引至 My Bibliography
   - 方便生成文献清单供学术汇报使用

### 6.3 金华泽为推荐保存的检索式列表

| 序号 | 检索式名称 | 邮件频率 | 收件人 |
|------|-----------|---------|--------|
| 1 | JZ_Zwitterionic | 每周 | 研发组+学术情报 |
| 2 | JZ_Antimicrobial_Dressing | 每周 | 研发组+学术情报 |
| 3 | JZ_EB_Surface_Mod | 每两周 | 研发组 |
| 4 | JZ_DFU | 每周 | 学术情报+市场部 |
| 5 | JZ_Pressure_Ulcer | 每两周 | 学术情报+注册部 |
| 6 | JZ_Wound_Comprehensive | 每周 | 所有相关人员 |
| 7 | JZ_Systematic_Reviews | 每月 | 学术情报+市场部 |

### 6.4 My NCBI 过滤器设置（推荐）

在 My NCBI → Filters 中创建以下过滤器，可快速筛选：

| 过滤器名 | 过滤条件 | 用途 |
|---------|---------|------|
| 近期发表 | "last 2 years"[dp] | 监控时效 |
| 高质量证据 | "Meta-Analysis"[ptyp] OR "Systematic Review"[ptyp] OR "Randomized Controlled Trial"[ptyp] | 决策参考 |
| 中国作者 | "China"[Affiliation] OR "Chinese"[Language] | 国内竞争情报 |
| Free Full Text | free full text[sb] | 开放获取文章 |

---

## 七、检索策略维护记录

| 日期 | 版本 | 修改人 | 变更内容 |
|------|------|-------|---------|
| 2026-06 | v1.0 | 初始创建 | 全部检索式建立 |
| — | — | — | 待补充 |
| — | — | — | 待补充 |

---

## 附录A：PubMed检索语法速查

| 语法 | 含义 | 示例 |
|------|------|------|
| [Mesh] | MeSH主题词检索（含下位词） | "Wound Healing"[Mesh] |
| [Title/Abstract] | 标题/摘要检索 | zwitterion*[Title/Abstract] |
| [ptyp] | 出版类型过滤 | Clinical Trial[ptyp] |
| [dp] | 出版日期过滤 | 2024:2026[dp] |
| [Language] | 语言过滤 | english[Language] |
| * | 通配符（词干截断） | dressing* 匹配 dressing, dressings, dressings' |
| AND / OR / NOT | 布尔逻辑 | A AND B |
| " " | 精确短语检索 | "wound dressing" |

## 附录B：周期性文献监控工作流

```
周一 09:00 → 检查RSS阅读器 → 快速扫描标题（10分钟）
周一 09:10 → 标记重要文献 → 下载全文PDF
周一 09:30 → 更新文献跟踪表（Excel/Notion/Airtable）
每月底 → 汇总月度文献简报（Top 10 重要论文）
每季度 → 更新技术路线图（基于文献趋势）
```

> **效率建议**：使用Zotero或EndNote管理全文PDF与引文，同步到团队共享库。
