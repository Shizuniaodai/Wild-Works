# 第二课作业：Ubuntu 22.04 环境搭建与命令练习

- 姓名：李雨涵
- 学号：1120262502
- 提交日期：2026-11-17

## 一、环境与工具

| 项目 | 内容 |
|---|---|
| 虚拟化方式 | Docker 容器（官方镜像 `ubuntu:22.04`） |
| 宿主环境 | GitHub Codespaces（Windows 11 上的浏览器） |
| Linux 发行版 | Ubuntu 22.04 LTS（`lsb_release -a` 见截图 01） |
| 终端 | 浏览器内终端（bash） |
| Agent 工具 | DeepSeek Harness（Web 端），用于生成命令、解释报错、给出排查顺序 |

## 二、截图清单

| 编号 | 文件 | 内容 |
|---|---|---|
| 01 | `截图/01_环境版本.png` | `lsb_release -a`、`uname -a`、`cat /etc/os-release` |
| 02 | `截图/02_目录定位.png` | `pwd`、`cd`、`ls -la`、`mkdir -p` 的连续操作 |
| 03 | `截图/03_文件操作.png` | `touch`、`cp`、`mv`、`rm`、`ls -l` |
| 04 | `截图/04_文本查看.png` | `cat`、`head`、`tail`、`wc -l`、`grep -n` |
| 05 | `截图/05_Agent辅助.png` | Agent 界面中的分析步骤与命令方案 |

## 三、心得（约 200 字）

这次我用 Docker 起了一个 `ubuntu:22.04` 容器来练命令，容器是空的，很多工具要自己装。Agent 主要帮了三件事：先让我用 `lsb_release -a` 和 `uname -a` 确认版本；再把要练的命令按目录定位、文件操作、文本查看分好组，省去我一条条查参数；我卡住时它会先看报错原文，再给排查顺序。

遇到的问题主要有两个。一是容器里没有 `lsb_release`，直接敲报 `command not found`，先 `apt-get update` 再装 `lsb-release` 才有输出，这时才明白“镜像最小化”是什么意思。二是习惯在 Windows 里点文件，到了命令行里 `cd` 过去发现目录是空的，用 `pwd` 和 `ls -la` 确认当前位置之后才找到原因。

收获是：命令行本身不难，难在不知道下一步该用什么命令。Agent 能把“我想做什么”翻译成具体指令，出错时也能指出是哪一段的问题。但命令还是要自己敲一遍，参数的意思才记得住。

## 四、遇到的问题与解决

| 问题 | 现象 | 解决 |
|---|---|---|
| 缺命令 | `lsb_release: command not found` | `apt-get update && apt-get install -y lsb-release` |
| 路径混淆 | `cd` 到某个目录后看不到刚建的文件 | 用 `pwd` 确认当前目录，`ls -la` 确认文件是否真的存在 |
| 中文乱码 | 终端里中文显示成方块 | 换用支持中文的等宽字体 |

## 五、备注

- 未上传虚拟机镜像、ISO 或 Docker 导出包。
- 截图中不包含密码、令牌或与作业无关的个人信息。
