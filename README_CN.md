# 我的 st 构建

[English](README.md) | 简体中文

[st](https://st.suckless.org/) 是一个 Xorg 下简洁的的终端模拟器.

## 要求

为了构建 st 你需要 Xlib 头文件.

所以在编译之前请安装 `libxinerama` 和 `libx11`.

## 使用的补丁

- [st-alpha-0.8.2.diff](https://st.suckless.org/patches/alpha/)
- [st-anysize-0.8.1.diff](https://st.suckless.org/patches/anysize/)
- [st-nordtheme-0.8.2.diff](https://st.suckless.org/patches/nordtheme/)
- [st-scrollback-0.8.4.diff](https://st.suckless.org/patches/scrollback/)

## 安装

编辑 config.mk 文件来匹配你的本地设置(st 默认安装在 /usr/local)

然后使用以下命令来构建并安装 st (以 root 权限运行):


    make clean install


## 运行 st

如果你没有使用 `make clean install` 来安装 st,
你必须通过以下命令编译 st terminfo:


    tic -sx st.info


转到 man page 来获得额外的细节信息.

如果你使用 dwm, 默认情况下你可以使用你设置的快捷键来运行 st.

如果不行, 检查你的 config.h 文件 并确保你的 termcmd 变量像这样:


    static const char *termcmd[]  = { "st", NULL  };


并在 keys 变量中设置对应的快捷键.
