# XN TOOL

PUBG MOBILE 一体化修改工具: **PAK 解包 / 打包 / 加密保护 + Lua 反编译 / 编译**

支持五服: GL(国际) | TW(台服) | VN(越服) | KR(日韩服) | BGMI(印度服)

当前游戏版本: 4.6

---

## 一键安装 (Termux)

```bash
pkg update -y && pkg upgrade -y && pkg install -y git openjdk-17 lua53 clang && termux-setup-storage && rm -rf ~/XN && git clone https://github.com/BYXIAN6/XNTOOL.git ~/XN && printf '#!/data/data/com.termux/files/usr/bin/sh
exec $HOME/XN/XN "$@"
' > $PREFIX/bin/xn && chmod +x $PREFIX/bin/xn && cd ~/XN && chmod +x XN && echo "" && echo "========================================" && echo "  安装完成! 输入 xn 启动工具" && echo "  (首次启动自动下载依赖)" && echo "========================================"
```

装完后**输入 `xn` 即可启动** (任意目录有效)。

## 更新工具

重新执行上面的安装命令即可 (会自动清理旧版)。

已装用户也可以:

```bash
rm -rf ~/XN && git clone https://github.com/BYXIAN6/XNTOOL.git ~/XN && chmod +x ~/XN/XN
```

---

## 功能

| 模块 | 功能 |
|---|---|
| PAK 解包 | 解密所有官方加密格式, 解出游戏文件 |
| PAK 打包 | 支持按目录结构打包 / index.csv 自定义重装 (可注入全新文件) |
| PAK 加密保护 | 整体 SM4-47 重加密, 防他人解包 |
| Lua 反编译 | 批量 / 单文件, 游戏字节码 → 可读源码 |
| Lua 编译 | 源码 → 游戏字节码 (自动兼容 4.4 操作码表) |

## 目录说明

首次启动自动创建 `/storage/emulated/0/Download/XNTOOL/`:

```
PAK_ORIGINAL   放原版 .pak
PAK_UNPACK     解包输出
RESULT_PAK     打包输出
LUA_ORIGINAL   原版 lua (反编译输入)
LUA_UNPACK     反编译输出 (改这里)
LUA_EDIT       编译输出
```

打包时 edited/ 为空会自动使用 LUA_EDIT 目录的文件。

## 常见问题

- **首次启动要下载依赖** (jar + 索引, 约 15MB), 之后每次会话只下一次, 退出自动清理。
- 反编译需要 java、编译需要 lua53, 安装命令已自动装好。
- 工具更新跟随游戏版本, 游戏大更新后请重新执行安装命令获取新版。

---

### XN WARNING | @XIANOBB
