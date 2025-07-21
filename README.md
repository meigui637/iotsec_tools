   一款针对 IoT 固件的图形化渗透测试工具，支持解包分析、接口扫描、用户模拟、敏感信息提取、FirmAE交互等多个安全评估功能
IoT Firmware Pentest Tool

图片
<img width="1006" height="825" alt="image" src="https://github.com/user-attachments/assets/a38f468a-f43d-468d-bb67-2aa23aba1712" />


✨ 功能特点
🧩 固件解包：一键调用 binwalk 解包并自动判断加密情况。

🌐 未授权接口扫描：输入固件模拟 IP，自动探测 HTML/JS/PHP 等页面是否可直接访问。

👤 用户模拟：识别架构并自动使用 QEMU + chroot 模拟用户操作，尝试运行 Web 服务。

🧠 FirmAE交互：图形化配置并启动 FirmAE 自动化漏洞分析框架。

🔍 敏感信息分析：集成 Firmwalker，快速扫描配置、密码、脚本、私钥等敏感内容。

🧼 清屏控制台：每个功能页面支持独立清屏，保持日志整洁。

📦 模块化结构：每个功能模块独立为 .py 文件，易于扩展与维护。

📦 安装依赖
建议在 Linux 环境下运行。

bash
复制
编辑
sudo apt update
sudo apt install python3-pyqt5 binwalk qemu-user-static -y
pip install requests
确保你已安装：

binwalk

qemu-arm-static, qemu-mips-static, qemu-aarch64-static

gnome-terminal 或 xterm

🚀 使用说明
bash
复制
编辑
sudo python3 main.py
注意：工具中部分功能（如 chroot）需要 root 权限。


📂 目录结构
bash
复制
编辑
iot_firmware_tool/
├── main.py                  # 主界面程序
├── unpacker.py              # 固件解包模块
├── scanner.py               # 未授权页面扫描模块
├── user_emulator.py         # 用户模拟模块
├── firmae_runner.py         # FirmAE交互模块
├── firmwalker_runner.py     # 敏感信息分析模块
├── firmwalk_result/         # 分析结果目录
└── README.md                # 项目说明文档


🧠 使用案例
对某品牌固件进行快速解包和加密识别

模拟真实运行环境，执行 /bin/httpd、goahead、boa 等服务

检测未授权访问页面，如 /admin.html、/config.js

利用 Firmwalker 抓取私钥、密码、硬编码账户等

