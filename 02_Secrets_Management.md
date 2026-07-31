# Secrets Management

## 这个文件是谁用的

这是给 Codex / Agent 在所有项目里处理 API token、邮箱授权码、Discord bot token 等密钥时读取的通用规则。

它只记录密钥应该放在哪里、怎么找、怎么让用户补充；不要在这里写任何真实密钥值。

## 默认密钥位置

用户本机的 BorgRise 相关密钥统一放在：

```text
/Users/ison/.borgrise/secrets/
```

常见文件命名：

```text
/Users/ison/.borgrise/secrets/boj.env
/Users/ison/.borgrise/secrets/<campaign>.env
/Users/ison/.borgrise/secrets/<system>.env
```

BOJ creator ops 当前默认读取：

```text
/Users/ison/.borgrise/secrets/boj.env
```

## 查找顺序

当项目需要密钥时，优先按这个顺序找：

1. 项目文档或 README 里声明的 canonical secrets path。
2. `/Users/ison/.borgrise/secrets/<campaign>.env`。
3. `/Users/ison/.borgrise/secrets/<system>.env`。
4. 项目本地兼容路径，例如 `secrets/<campaign>.env`。
5. 旧项目里曾经使用过的 secrets 文件，只用于迁移，不作为长期入口。

## 旧密钥迁移规则

如果发现旧项目里散落着可复用密钥：

1. 只读取变量名和文件路径，不在对话里打印真实值。
2. 合并到 `/Users/ison/.borgrise/secrets/` 下对应 `.env` 文件。
3. 文件权限设置为 `600`。
4. 如果项目还需要兼容旧命令，可以生成项目本地 `secrets/<campaign>.env` 副本，但长期入口仍然是 `/Users/ison/.borgrise/secrets/`。
5. 更新项目 README / setup 文档，让新对话知道默认读取哪里。

## 需要用户补充新密钥时

不要让用户把密钥直接粘贴到聊天窗口。

应该这样做：

1. 先判断密钥属于哪个系统或 campaign。
2. 在 `/Users/ison/.borgrise/secrets/` 下创建或更新对应 `.env` 文件。
3. 写入变量名和空值，例如：

```env
NEW_SERVICE_API_KEY=
```

4. 告诉用户：已经建好本地文件，请她自己打开文件，把值填到等号后面。
5. 用户说填好后，再读取变量名确认是否存在，不打印值。

## 命名原则

优先使用清楚、可复用的变量名：

```env
TYPEFORM_TOKEN=
TYPEFORM_FORM_ID=
EMAIL_ADDRESS=
EMAIL_PASSWORD=
EMAIL_IMAP_HOST=
EMAIL_IMAP_PORT=
EMAIL_SMTP_HOST=
EMAIL_SMTP_PORT=
DISCORD_BOT_TOKEN=
DISCORD_GUILD_ID=
TIKHUB_TOKEN=
TIKHUB_API_KEY=
TIKHUB_BASE_URL=
FASTMOSS_API_KEY=
FASTMOSS_TOKEN=
TTPC_TOKEN=
```

如果服务已有官方变量名，优先沿用官方命名。

## 禁止事项

- 不要把真实密钥写进 GitHub。
- 不要在最终回复里展示真实密钥。
- 不要让用户把 token 粘贴进聊天窗口。
- 不要把 `.env` 文件加入 git。
- 不要因为找不到密钥就臆造可用状态。

## 回复用户时怎么说

如果需要用户补密钥，优先说：

```text
我已经在本地建好这个文件：/Users/ison/.borgrise/secrets/<name>.env
请你自己打开，把密钥填到对应变量后面。填好后告诉我，我会只检查变量是否存在，不会打印密钥值。
```
