# Meeting & Vocab Note Principles

## 这个文件什么时候用

当用户要求整理以下材料时，先读本文件，再开始执行：

- meeting transcript
- meeting notes
- SRT / subtitles
- course transcript
- Loom / Lark / Zoom transcript
- creator 1v1 notes
- vocabulary / expression extraction
- Obsidian note updates related to meetings, courses, creator commerce, or business English

用户常见触发语：

```text
先读 agent-operating-system 的 README，再按相关原则整理这个会议/SRT。
```

或：

```text
按 GitHub 里的会议笔记整理原则处理。
```

快捷指令：

```text
/meeting-notes
```

当用户使用这个指令时，默认是读取原则并执行整理；不要修改或推送原则库，除非用户另外明确要求。

## 核心目标

整理会议和课程时，不只是做摘要，而是把内容沉淀成以后能复用的知识资产。

每次整理都要尽量帮助用户积累：

- 产品怎么卖
- 达人怎么表达
- 商家怎么谈
- 内容结构怎么拆
- 哪些英文表达可以直接练习和复用

## 默认归档位置

优先更新已有主文档，不轻易新建很多零散小文件。

当前默认位置：

- Creator 1V1: `04_Creator_1v1/KBSP Creator 1V1 Key Takeaways.md`
- Creator 1V1 English practice: `04_Creator_1v1/KBSP Creator 1V1 English Practice.md`
- GGO course notes: `08_GGO/GGO Course Key Takeaways.md`
- GGO English practice: `08_GGO/GGO English Practice.md`
- KBSP meeting English practice: `01_Meetings/KBSP Meeting English Practice.md`
- 通用英文表达: `02_Vocab/KBSP Meeting Vocab.md`
- Direct reader: `00_Index/KBSP Learning Reader.html`
- 已并入主文档的来源笔记: `Archive/`
- 模板: `Templates/`

只有当内容明显属于新主题、新项目、新长期板块时，才新建文件夹或主文档。

## Obsidian 阅读体验

主文档要服务阅读和复习，而不是只服务保存。

整理时默认做到：

- 最新内容有清晰的 `Latest Entry` 或最新区块入口。
- 主文档有 `目录`、`Quick Jump`、`Course map` 或同类导航。
- 新增内容后同步更新最新入口。
- 旧的单独笔记如果已经并入主文档，移到 `Archive/`，不留在主工作流里干扰阅读。
- 不保留死链接、空页面链接、过期入口。
- 文件夹命名保持干净，例如 `08_GGO`、`07_RedNote`，不要出现多余空格或不明编号。

## 学习型布局：精华和练习分开

当材料同时包含方法论和英文表达时，优先拆成两类文件：

- Key Takeaways / Notes: 放课程精华、会议判断、产品逻辑、达人方法论、复盘框架。
- English Practice: 放可直接开口练习的英文表达、中文反推英文、替换练习、mini drill。

不要把大量英文表达塞在精华主文档里，除非只是少量关键词。主文档应该服务理解和决策，练习文档应该服务开口和复用。

英语练习文件推荐格式：

```md
### 1. recent momentum - 近期增长势头

**可直接说：**
- `The product sold well before, but we need to check if it still has recent momentum.`

**中文反推英文：**
- 这个产品以前卖得好，但我们要看它最近是否还有增长势头。

**替换练习：**
- Replace `product` with `campaign`, `creator`, `category`, or `content angle`.
```

必要时增加 `Mini Drills`，把 2-4 句表达组合成一个可以在会议或 creator feedback 里直接说的小段落。

## 最新内容优先

用户明确偏好打开文件后先看到最新内容。

整理时默认做到：

- 最新会议 / 课程 section 放在主文档前部，或至少在顶部 `Latest Entry` 里直接跳转。
- 练习文件最新 section 放在旧表达 bank 前面。
- 旧内容可以保留在下方作为 archive / earlier bank，不要让旧内容挡在最新内容前面。
- 如果原文件太大、不适合整体倒排，采用低风险做法：顶部新增 `Latest Entry` 和 `Quick Jump Latest First`，不强行搬动全文。

## 直达阅读入口

如果用户表示懒得打开 Obsidian、想直接看到更漂亮的阅读版，优先维护本地 HTML reader，而不是要求用户改变阅读习惯。

当前 KBSP vault 的直达阅读入口：

- HTML: `00_Index/KBSP Learning Reader.html`
- Build script: `.tools/build-kbsp-reader.js`
- Desktop shortcut: `/Users/ison/Desktop/KBSP Learning Reader.webloc`

当更新被 reader 收录的主文档或练习文档时，整理完成后运行：

```bash
node ".tools/build-kbsp-reader.js"
```

然后用户可以双击桌面 `KBSP Learning Reader.webloc` 直接打开阅读版。

## 会议 / 课程精华怎么提炼

不要逐字搬运 transcript。重点提炼可复用的判断、框架、方法和表达。

优先捕捉：

- speaker 的真实思路
- 为什么这么判断
- 为什么这个产品这样卖
- 为什么这个 hook / CTA / objection handling 有效
- 这个内容对达人、品牌谈判、内容创作有什么复用价值

每个模块尽量回答：

- 这节在教什么？
- 核心判断是什么？
- 可复制的方法是什么？
- 对用户以后做达人、谈商家、做内容有什么帮助？

对重复内容做合并，不为了显得完整而反复写同一个观点。

## SRT / Transcript 处理规则

处理 SRT 或长 transcript 时：

- 按用户给定顺序处理。
- 自动忽略 SRT 序号和时间轴，只保留内容。
- 长文本可以分段读取，但最终输出要合并成结构化笔记。
- 不把大量原文塞进笔记。
- 只有当某句话本身特别值得练习时，才作为表达收录。
- 如果 transcript 有明显转写错误，整理时修成自然英文，但不改变原意。

## 英语表达收录原则

表达收录要实用，不要贪多。

优先收：

- 商务沟通表达
- 策略复盘表达
- 产品判断表达
- 执行管理表达
- 谈判推进表达
- 客户 / 达人沟通表达
- 能跨行业复用的 business English

不要优先收：

- 太依赖 TikTok Shop 具体语境的术语
- 太口水、太碎、太情绪化的句子
- 只在某个视频案例里成立的表达
- 已经在词库里收过、没有新用法的重复表达

如果表达只适合课程内部理解，放在课程笔记。  
如果表达在商业场景也常用，再同步进 `02_Vocab/KBSP Meeting Vocab.md`。

## 英语表达呈现格式

新增表达放在 Vocab 文件前面，方便复习和检索。

每条表达尽量包含：

- 英文表达
- 中文含义
- 使用场景
- 1-2 个实用例句

例句要像真实会议、谈判、复盘、工作消息里会说的话。避免写成考试作文。

推荐格式：

```md
### 1. build on what's proven — 基于已验证的东西继续做

**含义：** 不从零开始乱试，而是在已验证方向上迭代。

**例句：**
- `We don't need to start from scratch. We can build on what's proven.`
  *（我们不需要从零开始，可以基于已验证的东西继续做。）*
- `For the next batch, let's build on what's proven and only test one new variable.`
  *（下一批我们基于已验证的方向，只测试一个新变量。）*
```

## 文件夹和命名规则

正式内容文件夹用数字排序：

```text
00_Index
01_Meetings
02_Vocab
03_Playbooks
04_Creator_1v1
08_GGO
```

非主线资料不用强行编号：

```text
Archive
Templates
```

命名原则：

- 主文档名称要清楚表达用途。
- 文件夹名不要有多余空格。
- 不保留 `.DS_Store` 这类系统缓存文件。
- 已合并进主文档的旧笔记优先归档，不直接删除。

## 主动执行原则

拿到资料后，不要等用户一步一步催。

默认完整执行：

1. 读取资料。
2. 判断应该写入哪个主文档。
3. 提炼课程 / 会议精华。
4. 提取可复用英文表达。
5. 检查旧词库，避免明显重复。
6. 写入对应 Obsidian 主文档。
7. 如果有可练习表达，写入对应 English Practice 文件，而不是只塞进主文档。
8. 更新 `Latest Entry`、目录或 quick jump。
9. 如果存在本地 HTML reader，重新生成 reader。
10. 检查 Obsidian 内链和占位符。
11. 简洁告诉用户更新了哪里。

低风险整理可以直接做，例如：

- 更新目录
- 修正死链接
- 移动已归档源笔记
- 清理 `.DS_Store`
- 更新 `Latest Entry`
- 重新生成本地 HTML reader

高风险操作先说明判断，再谨慎执行，例如：

- 删除有内容价值的文件
- 大规模改名
- 改动核心目录结构
- 公开或推送可能包含敏感信息的内容

## 最终交付标准

一次合格的整理应该满足：

- 文档打开后能快速知道最新整理到哪里。
- 课程精华能帮助用户复盘方法论。
- 英语表达能拿来练习和复用。
- 精华文档和练习文档职责清楚，不互相污染。
- 如果用户有直达阅读入口，reader 已同步到最新内容。
- 文件夹结构清爽，主入口明确。
- 旧材料不干扰当前阅读。
- 下次处理新会议或新 SRT 时，读本文件即可延续同一套标准。
