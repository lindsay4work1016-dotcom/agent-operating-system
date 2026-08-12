# Agent Operating System

这是一个跨项目、跨对话使用的通用 Agent 工作原则库。

它不属于 BOJ，也不属于任何单一客户项目。以后无论是新品牌、新系统、新自动化，或者新的长期对话，都可以先读这里，再读具体项目自己的 README / context / playbook。

## 这个库解决什么问题

当一个对话里积累了很多有价值的信息，但新对话又不能完整继承上下文时，不要每次靠手写长 prompt 复述。

更稳定的做法是：

1. 把通用对话原则写在这个 GitHub 仓库里。
2. 把具体项目规则写在项目自己的 GitHub 或项目文件夹里。
3. 新对话开始时，先读取这里，再读取具体项目入口。

## 文件目录

| 文件 | 用途 |
| --- | --- |
| `README.md` | 本目录索引，也是 GitHub 主页 |
| `00_Global/01_Objective_Conversation_Principles.md` | 所有对话都遵循的客观、理性、可验证原则 |
| `00_Global/02_Secrets_Management.md` | 本机密钥统一管理位置、查找顺序、补充新密钥的规则 |
| `10_Workflows/01_Meeting_Vocab_Note_Principles.md` | 从会议、SRT 和课程 transcript 提炼知识与英文表达时使用的工作流原则 |
| `10_Workflows/02_Obsidian_Knowledge_Base_Maintenance.md` | 把材料写入 Obsidian、维护导航并清理已合并源文件时使用的通用工作流 |

## 目录结构

```text
agent-operating-system/
  README.md
  00_Global/
    01_Objective_Conversation_Principles.md
    02_Secrets_Management.md
  10_Workflows/
    01_Meeting_Vocab_Note_Principles.md
    02_Obsidian_Knowledge_Base_Maintenance.md
```

## 原则调用顺序

新对话或新任务开始时，默认先读本 `README.md`。

然后按任务类型只读取相关文件，不要为了保险把所有原则都加载一遍：

- 所有任务都适用：读取 `00_Global/01_Objective_Conversation_Principles.md`
- 涉及密钥、token、`.env`、API 授权：读取 `00_Global/02_Secrets_Management.md`
- 涉及会议、SRT、课程 transcript、词组整理：读取 `10_Workflows/01_Meeting_Vocab_Note_Principles.md`
- 涉及 Obsidian 写入、合并、归档、目录维护或源文件清理：读取 `10_Workflows/02_Obsidian_Knowledge_Base_Maintenance.md`，再读取当前项目自己的入口和维护规则

## 新对话通用开场白

如果你希望新对话先进入稳定工作状态，可以复制这段：

```text
请先读取我的通用 Agent 工作原则：
https://github.com/lindsay4work1016-dotcom/agent-operating-system

然后再处理我接下来的具体任务。
请保持客观、理性、可验证；不要盲从我的猜测；能查证的先查证，不能查证的明确标记为待确认。
```

如果是某个具体项目，再追加：

```text
这个项目的入口是：这里填 GitHub 链接或本地路径。
请先读取项目 README 和相关 playbook，再开始执行。
```

如果是会议、课程或词组整理，可以直接说：

```text
请先读取 agent-operating-system 的 README，再按会议和词组整理原则处理这份材料。
```

## 快捷指令

如果用户输入：

```text
/meeting-notes
```

含义是：

- 先读取本 `README.md`。
- 再读取 `10_Workflows/01_Meeting_Vocab_Note_Principles.md`。
- 如果整理结果要写入 Obsidian，再读取 `10_Workflows/02_Obsidian_Knowledge_Base_Maintenance.md` 和当前项目规则。
- 按会议、SRT、课程 transcript、Obsidian 笔记和英文表达整理原则直接执行。
- 默认只执行整理任务，不修改本原则库，也不推送 GitHub。
- 只有当用户明确说“更新原则”“改 GitHub 里的规则”或“推送到 GitHub”时，才修改并推送本库。

## 维护原则

- GitHub 是这个通用原则库的唯一维护入口。
- 用户不需要在本地 Obsidian 里查看或维护这套文件。
- 通用原则放在这个库。
- 项目专属规则放在项目自己的仓库或项目目录。
- 不要把同一套说明复制到多个地方。
- 如果一条规则会影响所有对话，写进这里。
- 如果一条规则只影响某个项目，写进那个项目。
- 每次新增、删除、重命名通用规则文件，都必须同步更新本 README 的文件目录。
- 每次修改通用规则后，如果 README 里的说明也受影响，必须同步更新 README。
- 不要在根目录继续平铺新原则文件；通用底层原则放进 `00_Global/`，具体工作流原则放进 `10_Workflows/`。

## 归属判断

当用户说“记住这个”或“以后都这样”时，先判断规则归属：

- 所有对话都适用：写进这个库。
- 某个项目适用：写进项目自己的仓库或项目目录。
- 某次任务适用：只在当前任务执行，不写入长期文件。

如果不确定，先问一句它是通用规则还是项目规则。
