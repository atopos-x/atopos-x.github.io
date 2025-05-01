---
title: Linux
aliases: 
tags:
  - Linux
date: 2024-11-10
lastmod: 
time: 16:18
---
## Linux命令

**`ps` 命令**：

- `ps` 命令可以显示当前运行的进程的快照。
- `ps aux` 或 `ps -ef` 命令可以显示所有进程的详细信息，包括用户、进程ID（PID）、CPU使用率、内存使用率等。
- `ps aux`和`ps -aux`效果一样，`ps -aux`在某些系统上可能需要使用连字符来明确指定选项，特别是在某些较老的系统或某些特定的 shell 环境中。

``` sh
ps aux
ps -aux
ps -ef
```

**`top` 命令**：

- `top` 命令提供了一个动态的、实时更新的进程视图。
- 它会显示系统负载、CPU使用情况、内存使用情况以及各个进程的资源占用情况。

```sh
top
```

**`htop` 命令**：

- `htop` 是 `top` 的一个增强版本，具有更丰富的功能和更好的用户界面。
- 它需要安装后才能使用，可以通过包管理器安装，如 `apt-get install htop`（对于基于Debian的系统）或 `yum install htop`（对于基于RHEL的系统）。

```sh
htop
```

**`pgrep` 命令**：

- `pgrep` 命令可以根据名称或其他属性搜索进程，并返回匹配进程的PID。

```sh
pgrep firefox
```

**`systemctl` 命令**：

- 如果你想查看系统服务相关的进程，可以使用 `systemctl` 命令。

```sh
systemctl list-units --type=service
```

使用这些命令，你可以查看和管理Linux系统上的进程。每个命令都有其特定的用途和选项，你可以通过查看它们的帮助文档（通常是命令后跟 `-h` 或 `--help`）来了解更多信息。