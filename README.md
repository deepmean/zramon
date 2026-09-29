# zramon

为 JCG Q20 (LEDE 24.10.5 / 内核 5.10.252 / ramips-mt7621) 编译 `kmod-zram`。

## 背景

路由器运行 coolsnowwolf/lede 构建，内核 `5.10.252`，`CONFIG_HIGHMEM=n`，
内核中**不含** zram/zsmalloc。官方软件源无匹配 kmod，故云编译。

## 关键参数

| 项 | 值 |
|---|---|
| LEDE commit | `7df5d70268da` (kernel 5.10.252) |
| target | ramips/mt7621 |
| arch | mipsel_24kc |
| vermagic | `5.10.252 SMP mod_unload MIPS32_R2 32BIT` |
| HIGHMEM | **n**（关键，官方 22.03 模块为 y，故不兼容）|

## 产物

- `zsmalloc.ko` / `zram.ko`（HIGHMEM=n 编译）
- `kmod-zram_*.ipk` / `kmod-lib-lzo_*.ipk`
