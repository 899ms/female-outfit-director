# 安装与更新指南

## 前置条件

- 已安装支持本地 Skills 的 Codex 或兼容智能体。
- 本机可以使用 Git；也可以从 GitHub 下载 ZIP 后手动安装。
- 使用模特图或服装图时，建议选择具备图像理解能力的模型。

## macOS / Linux 安装

```bash
git clone https://github.com/liyue-aigc/female-outfit-director.git
mkdir -p ~/.codex/skills/ecommerce-fashion-tryon-director
cp -R female-outfit-director/skill/. ~/.codex/skills/ecommerce-fashion-tryon-director/
```

安装后的关键文件应位于：

```text
~/.codex/skills/ecommerce-fashion-tryon-director/SKILL.md
~/.codex/skills/ecommerce-fashion-tryon-director/agents/openai.yaml
~/.codex/skills/ecommerce-fashion-tryon-director/references/parameter-presets.md
~/.codex/skills/ecommerce-fashion-tryon-director/references/transition-library.md
```

## Windows PowerShell 安装

```powershell
git clone https://github.com/liyue-aigc/female-outfit-director.git
New-Item -ItemType Directory -Force "$HOME\.codex\skills\ecommerce-fashion-tryon-director"
Copy-Item -Recurse -Force ".\female-outfit-director\skill\*" "$HOME\.codex\skills\ecommerce-fashion-tryon-director\"
```

安装后的关键文件应位于：

```text
%USERPROFILE%\.codex\skills\ecommerce-fashion-tryon-director\SKILL.md
%USERPROFILE%\.codex\skills\ecommerce-fashion-tryon-director\agents\openai.yaml
%USERPROFILE%\.codex\skills\ecommerce-fashion-tryon-director\references\parameter-presets.md
%USERPROFILE%\.codex\skills\ecommerce-fashion-tryon-director\references\transition-library.md
```

## 下载 ZIP 安装

1. 在仓库页面选择 **Code -> Download ZIP**。
2. 解压下载文件。
3. 找到解压目录中的 `skill` 文件夹。
4. 将 `skill` 内部的全部内容复制到：
   - Windows：`C:\Users\你的用户名\.codex\skills\ecommerce-fashion-tryon-director\`
   - macOS / Linux：`~/.codex/skills/ecommerce-fashion-tryon-director/`
5. 确保 `SKILL.md` 直接位于 `ecommerce-fashion-tryon-director` 目录下，而不是额外嵌套在 `skill` 子目录中。

## 验证安装

重新打开 Codex 任务，然后输入：

```text
$ecommerce-fashion-tryon-director 请先介绍你能生成哪些电商服装换装素材方案。
```

如果 Skill 被正确识别，它会围绕模特、服装图、穿搭风格、套数、画幅、输出模式、首帧确认和商业质检来组织回答。

## 更新

在已克隆的仓库目录中执行：

```bash
git pull
cp -R skill/. ~/.codex/skills/ecommerce-fashion-tryon-director/
```

Windows PowerShell：

```powershell
git pull
Copy-Item -Recurse -Force ".\skill\*" "$HOME\.codex\skills\ecommerce-fashion-tryon-director\"
```

更新后新建一个 Codex 任务，以确保加载最新的 Skill 内容。

## 从旧版名称迁移

旧版示例可能使用 `$female-outfit-director`。商业版 Skill 的调用名称是：

```text
$ecommerce-fashion-tryon-director
```

如果本机已有旧版目录，可保留旧版，也可以删除旧目录后安装新版。删除本地 Skill 目录只影响 Skill 本身，不会删除已经生成的提示词、图片或视频。
