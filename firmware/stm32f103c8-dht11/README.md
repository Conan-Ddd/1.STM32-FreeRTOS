# STM32F103C8 + DHT11（当前进度）

这是个人学习工程的源码快照，不包含实习单位资料。来自桌面 `1.STM32-FreeRTOS/1.STM32-FreeRTOS`，上传时保留了原始的 CubeMX 配置、Core 源码、Keil 工程及启动文件。

## 当前状态

- MCU：STM32F103C8；系统时钟 72 MHz。
- PB1：DHT11_DAT，开漏输出；PA1：LED；USART1：PA9/PA10，115200 8N1。
- `main.c` 已初始化 GPIO/UART 并发送 `BOOT OK\r\n`。
- `dht11.c` 与 `dht11.h` 目前只有占位字符 `1`，尚未实现驱动，也尚未加入 Keil 的源文件列表。
- 尚未接入 FreeRTOS；此目录只是第一阶段的裸机练习工程。

## 在本机继续开发

1. 使用 STM32CubeMX 打开 `1.STM32-FreeRTOS.ioc`。工程配置的 STM32Cube FW_F1 版本为 V1.8.7、工具链为 MDK-ARM V5.32。
2. 重新生成代码，补齐本快照未上传的 STM32 HAL/CMSIS `Drivers/` 依赖；如果工具提示版本迁移，先备份并检查生成差异。
3. 用 Keil 打开 `MDK-ARM/1.STM32-FreeRTOS.uvprojx`。写好 DHT11 驱动后，在工程树中添加 `Core/Src/dht11.c`。
4. 接线和驱动步骤见 [第一个任务说明](../../docs/01-dht11-uart.md)。

本目录刻意未上传厂商库、编译输出、IDE 临时文件及板级资料。不要上传公司的原理图、PCB、固件或测试数据。
