# Agent Operating System

这是一个跨项目、跨对话使用的通用 Agent 工作原则库。

它不属于 BOJ，也不属于任何单一客户项目。以后无论是新品牌、新系统、新自动化，或者新的长期对话，都可以先读这里，再读具体项目自己的 README / context / playbook。

## 这个库解决什么问题

当一个对话里积累了很多有价值的信息，但新对话又不能完整继承上下文时，不要每次靠手写长 prompt 复述。

更稳定的做法是：

1. 把通用对话原则写在这个库里。
2. 把具体项目规则写在项目自己的 GitHub 或项目文件夹里。
3. 新对话开始时，先读取这里，再读取具体项目入口。

## 文件目录

| 文件 | 用途 |
| --- | --- |
| `README.md` | 本目录索引，也是 GitHub 主页 |
| `01_Objective_Conversation_Principles.md` | 所有对话都遵循的客观、理性、可验证原则 |

## 新对话通用开场白

如果你希望新对话先进入稳定工作状态，可以复制这段：

```text
请先读取我的通用 Agent 工作原则：
https://github.com/lindsay4work1016-dotcom/agent-operating-system

如果在本机 Codex 中工作，也可以读取本地路径：
/Users/ison/Documents/Ison-PKM/Ison Personal Knowledge Base/03_Playbooks/Agent Operating System/README.md
/Users/ison/Documents/Ison-PKM/Ison Personal Knowledge Base/03_Playbooks/Agent Operating System/01_Objective_Conversation_Principles.md

然后再处理我接下来的具体任务。
请保持客观、理性、可验证；不要盲从我的猜测；能查证的先查证，不能查证的明确标记为待确认。
```

如果是某个具体项目，再追加：

```text
这个项目的入口是：这里填 GitHub 链接或本地路径。
请先读取项目 README 和相关 playbook，再开始执行。
```

## 维护原则

- 通用原则放在这个库。
- 项目专属规则放在项目自己的仓库或项目目录。
- 不要把同一套说明复制到多个地方。
- 如果一条规则会影响所有对话，写进这里。
- 如果一条规则只影响某个项目，写进那个项目。
- 每次新增、删除、重命名通用规则文件，都必须同步更新本 README 的文件目录。
- 每次修改通用规则后，如果 README 里的说明也受影响，必须同步更新 README。

## 归属判断

当用户说“记住这个”或“以后都这样”时，先判断规则归属：

- 所有对话都适用：写进这个库。
- 某个项目适用：写进项目自己的仓库或项目目录。
- 某次任务适用：只在当前任务执行，不写入长期文件。

如果不确定，先问一句它是通用规则还是项目规则。
