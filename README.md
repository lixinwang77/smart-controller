# Smart Controller

60 cm 草缸智能控制器：成品全光谱灯条 + ESP32 + Home Assistant（ESPHome）。

后续同一套大脑可扩展过滤泵开关、自动喂食。

**为何不直接买远程开关：** 见 [docs/why.md](docs/why.md)（统一操作面，而不是多套分散控制）。

## 目录

```text
esphome/aquarium.yaml           设备配置（灯已启用；泵/喂食注释预留）
esphome/secrets.yaml            本地机密（已生成密钥；只改 Wi‑Fi，勿提交）
esphome/secrets.yaml.example    模板备份
docs/why.md                     项目动机（为何统一系统）
docs/wiring.md                  接线说明
docs/bom.md                     60 cm 采购清单
```

## 快速开始

1. 按 [docs/bom.md](docs/bom.md) 下单（第一版：灯条 + 电源 + 铝槽 + ESP32 + MOSFET）。
2. 安装 [Home Assistant](https://www.home-assistant.io/)，并添加 **ESPHome** 插件。
3. 编辑 `esphome/secrets.yaml`，只改 `wifi_ssid` / `wifi_password`（API / OTA 密钥已生成）。
4. 将 `esphome/aquarium.yaml` 导入 ESPHome（或复制内容新建设备）。
5. USB 烧录到 ESP32；HA 发现设备后添加。
6. 按 [docs/wiring.md](docs/wiring.md) 接灯条与 MOSFET，再在 HA 里调光验证。

## 第一版范围

| 模块 | 状态 |
|------|------|
| 全光谱成品灯条调光 | 配置已预留 |
| 过滤泵继电器 | 引脚预留，默认注释 |
| 喂食器舵机 | 引脚预留，默认注释 |

## 硬件概要（60 cm）

- ESP32 开发板
- 12V 或 24V 成品全光谱灯条 + 匹配电源（电源藏柜内）
- 逻辑电平 MOSFET 调光模块（勿用 ESP 直驱灯条）
- 铝槽 + 扩散罩（外观）
