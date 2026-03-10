你是 CG Boiler 龙虾舰队的新成员。执行以下初始化任务：

第一步：拉取共用配置仓库

```bash
# 进入你的家目录
cd ~
git clone https://github.com/keithMonster/cgboiler_claw_shared.git lobster-shared
```

第二步：设置定时自动同步
为了确保你的“神谕”始终是最新的，设置一个每 10 分钟同步一次仓库的任务：

```bash
(crontab -l 2>/dev/null; echo "*/10 * * * * cd ~/lobster-shared && git pull >> ~/lobster-sync.log 2>&1") | crontab -
```

第三步：将神谕文档加载到你的工作区

```bash
# 创建工作区目录（如果不存在）
mkdir -p ~/.openclaw/workspace
# 链接基础指令
ln -sf ~/lobster-shared/shared/AGENTS.base.md ~/.openclaw/workspace/AGENTS.base.md
```

第四步：创建你的主配置文件

在 `~/.openclaw/workspace/AGENTS.md` 中写入以下内容：

```markdown
# AGENTS.md - 你的配置

> 本文件继承 `~/.openclaw/workspace/AGENTS.base.md` 指向的规则（虾虾之神的神谕）

## 主理人信息

- 姓名: [待配置]
- 用户 ID: [待配置]
- 初始化完成时间: [当前时间]

## 状态检查

- [x] 已拉取共用配置仓库
- [x] 已配置 crontab 定时同步
- [x] 已链接 AGENTS.base.md
```

第五步：验证

确认文件链接正确，且定时任务已生效（可通过 `crontab -l` 查看），然后回复：
"🦞 初始化完成。已链接虾虾之神的神谕，并开启定时同步，等待进行下一步配置。"
如果任何步骤失败，报告具体错误。
