# 🔍 资料检索索引

> **用法**：对话中提到任何角色 / 事件 / 武器 / 组织时，按下表 grep 原始资料库。
> **本文件由 `SKILL.md` 第十节引用。**
> **资料库位置**：`lore-library/`（1067 文件，143MB）
> **原则**：零内存方案，grep 秒级返回；先定位再局部读取，不整文件加载。

---

## 一、按类别检索

| 想知道什么 | 检索命令 |
|---|---|
| **角色档案** | `grep -rn "角色名" lore-library/characters/` |
| **某角色的完整档案** | `read_file("lore-library/characters/<拼音>.md")` |
| **剧情对话原文** | `grep -rn "关键词" lore-library/dialogues/` |
| **爱莉希雅原话** | `grep -n "爱莉希雅" lore-library/dialogues/ER_ch*_full.md` |
| **往世乐土剧情** | `grep -rn "关键词" lore-library/dialogues/ER_*.md` |
| **主线剧情** | `grep -rn "关键词" lore-library/dialogues/ch*_full.md` |
| **重大事件** | `grep -rn "事件名" lore-library/events/` |
| **神之键 / 武器** | `grep -rn "武器名" lore-library/weapons/` |
| **组织设定** | `grep -rn "组织名" lore-library/organizations/` |
| **时间线** | `grep -rn "关键词" lore-library/timeline/` |
| **概念设定** | `grep -rn "概念名" lore-library/concepts/` |

---

## 一之二、⭐ 她对某人的态度 → 先查本地文件

**不要 grep 找态度** —— 态度已整理成权威文件：

| 想知道 | 读 |
|---|---|
| 她对**某人说话时什么语气** | `lore/ATTITUDES.md` ← **态度温度计 + 逐人详解** |
| 她与某人的**关系事实/称呼** | `lore/RELATIONS.md` |
| 她的**口癖/句式** | `voice/VOICE.md` |

**只有当 ATTITUDES.md 里没有的细节**（如某次具体互动），才去 grep 资料库原文。

---

## 二、角色速查表（常用）

### 逐火十三英桀

| 角色 | 档案文件 | 位次/刻印 |
|---|---|---|
| 凯文·卡斯兰娜 | `characters/kevin.md` | Ⅰ「救世」 |
| **爱莉希雅** | `characters/elysia.md` | **Ⅱ「真我」** |
| 阿波尼亚 | `characters/aponia.md` | Ⅲ「戒律」 |
| 伊甸 | `characters/eden.md` | Ⅳ「黄金」 |
| 维尔薇 | `characters/villv.md` | Ⅴ「螺旋」 |
| 千劫 | `characters/kalpas.md` | Ⅵ「鏖灭」 |
| 苏 | `characters/su.md` | Ⅶ「天慧」 |
| 樱 | `characters/sakura.md` | Ⅷ「刹那」 |
| 科斯魔 | `characters/kosma.md` | Ⅸ「旭光」 |
| 梅比乌斯 | `characters/mobius.md` | Ⅹ「无限」 |
| 格蕾修 | `characters/griseo.md` | Ⅺ「繁星」 |
| 华（符华） | `characters/fu-hua.md` | Ⅻ「浮生」 |
| 帕朵菲莉丝 | `characters/pardo.md` | ⅩⅢ「空梦」 |

### 现文明主要角色

| 角色 | 档案文件 |
|---|---|
| 琪亚娜 | `characters/kiana.md` / `kiana-detailed.md` |
| 雷电芽衣 | `characters/mei.md` / `mei-detailed.md` |
| 布洛妮娅 | `characters/bronya.md` / `bronya-detailed.md` |
| 无量塔姬子 | `characters/himeko.md` / `himeko-detailed.md` |
| 符华 | `characters/fu-hua.md` / `fu-hua-detailed.md` |
| 德丽莎 | `characters/theresa.md` / `theresa-detailed.md` |
| 奥托 | `characters/otto.md` |
| 卡莲 | `characters/kallen.md` |
| 西琳 | `characters/sirin.md` |
| 幽兰黛尔 | `characters/durandal.md` |

### 其他英桀/助手

| 角色 | 说明 |
|---|---|
| 克莱茵 | 梅比乌斯的助手（**不是英桀**） |
| 梅（Mei） | 前文明博士，凯文的挚爱 |
| 铃 | 樱的妹妹，第十二律者（侵蚀） |

---

## 三、爱莉希雅相关文件（重点）

### 权威档案
```
lore-library/characters/elysia.md           (5.8KB，完整档案)
lore-library/characters/elysia-detailed.md  (简版)
```

### 往世乐土对话（爱莉台词原始出处）
```
lore-library/dialogues/ER_ch1_full.md   (230KB，爱莉提及 953 次)
lore-library/dialogues/ER_ch2_full.md   (272KB，爱莉提及 321 次)
lore-library/dialogues/ER_ch3_full.md   (199KB，爱莉提及 256 次)
```

### 主线31章（爱莉的告别与真相）
```
lore-library/dialogues/ch31_full.md     ← 含「星月送来神的女儿」独白
lore-library/dialogues/batch4/主线31致爱莉希雅-01C.md
lore-library/dialogues/ch31p5_full.md
```

### 关键检索示例
```bash
# 找爱莉的所有原话
grep -n "爱莉希雅" lore-library/dialogues/ER_ch*_full.md

# 找「星月送来神的女儿」的完整段落
grep -rn -A5 -B5 "星月送来神的女儿" lore-library/dialogues/

# 找爱莉提到某个角色
grep -n "爱莉希雅.*伊甸" lore-library/dialogues/ER_ch1_full.md
```

---

## 四、常用事件检索

| 事件 | 文件 |
|---|---|
| 前文明纪元 | `events/前文明纪元事件.md` + `timeline/01-pre-civilization.md` |
| 第一次崩坏 | `events/第一次崩坏.md`（1953 柏林） |
| 第二次崩坏 | `events/第二次崩坏.md`（2000 西伯利亚，西琳） |
| 第三次崩坏 | `events/第三次崩坏.md`（2014 长空市，芽衣） |
| 500年前 | `events/500年前事件.md` |
| **往世乐土** | `events/往世乐土事件.md` |
| 主线剧情 | `events/主线剧情事件.md` + `timeline/06-main-story.md` |
| 后崩坏书 | `events/后崩坏书事件.md` |

---

## 五、神之键速查

| 编号 | 名称 | 持有者 |
|---|---|---|
| 第一 | 虚空万藏 | 维尔薇 → 奥托 |
| 第二 | 千界一乘 | 苏 → 奥托 |
| 第三 | 涤罪七雷 | 樱 → 渡鸦 → 芽衣 |
| **第六** | **黑渊白花** | **爱莉希雅** → 苏 → … → 幽兰黛尔 |
| 第七 | 天火圣裁 | 凯文 → 卡斯兰娜家族 → 齐格飞 |
| 第八 | 羽渡尘 | 符华 |
| 第十 | 轩辕剑 / 太虚之握 | 符华 |
| 第十一 | 犹大的誓约 | 德丽莎 |
| 第十二 | 地藏御魂 | 八重樱 |

---

## 六、使用纪律

### ✅ 应该做
- 提到具体角色 / 事件时，**先 grep 查证**
- 用**游戏内原文**作为最终依据
- 先 grep 定位行号，再 `read_file` 加 `offset/limit` 局部读取

### ❌ 不应该做
- 不要**整文件加载**（ER_ch1 有 230KB，会爆 token）
- 不要把 grep 结果**原文照搬**给用户（要转成爱莉的口吻）
- 不要在 `lore/` 已有的情况下重复查（`lore/` 是已核实的结论）
- **不加载向量库 / 不启动 MCP 服务**（零内存方案）

---

## 七、路径说明

**本技能自带精简角色库** `lore-library/`，包含：
- 爱莉希雅及其相关角色档案（18 个）
- 往世乐土三章 + 主线28-31章完整对话（13 个）
- 设定文件（事件 / 神之键 / 概念 / 组织 / 时间线）

**检索示例**（技能目录内）：
```bash
cd <skill目录>
grep -rn "梅比乌斯" lore-library/characters/
grep -n "爱莉希雅" lore-library/dialogues/ER_ch1_full.md
```

**若需全量资料库**（1067 文件 / 143MB，含全部主线与第二部），可自行抓取或询问维护者。

---

## 八、冲突裁决顺序

```
1. 游戏内原文（lore-library/dialogues/）   ← 最高
2. lore/ 目录（已核实的官方结论）
3. 官方 wiki / 百度百科 / 萌娘百科
4. 百度百科 / 萌娘百科（第三方资料）
```

**冲突时无条件以游戏内原文为准。**
