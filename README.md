# xpu-smi for ARC770

## 查看帮助

查看所有可 dump 的指标：

```bash
sudo xpu-smi dump -help
```

## 常用 dump 指标

| 指标编号 | 含义 |
|----------|------|
| 0        | GPU 利用率 (GPU Utilization) |
| 1        | GPU 频率 (GPU Frequency) |
| 2        | GPU 核心温度 (GPU Core Temperature) |
| 3        | GPU 功耗 (GPU Power) |
| 18       | GPU 内存使用量 (GPU Memory Used) |
| 22       | GPU EU 利用率 / 引擎利用率 (EU Array Active) |

## 查看 GPU 利用率

> ⚠️ **注意：查看 GPU 利用率需要指定指标 22，单独使用指标 0 会显示N/A！**

```bash
sudo xpu-smi dump -m 0,22 -d 0
```

## 常用组合示例

```bash
# 同时查看利用率、频率、温度、功耗、内存、EU利用率
sudo xpu-smi dump -m 0,1,2,3,18,22 -d 0
```

> 参数说明：
> - `-m`：指定要 dump 的指标编号（逗号分隔）
> - `-d`：指定设备编号（0 表示第一块 GPU）
