# PumpFun Tools - PumpFun工具集

一个功能强大的PumpFun工具集合，包含钱包管理、虚拟地址生成和交易执行等功能。

联系我：https://t.me/Pornhub_CNC

请勿进行倒卖！！！！！！！！

## 效果图
<img width="1280" alt="image" src="https://github.com/user-attachments/assets/4605b306-467c-4d39-a28a-fa2a44fc33af">
<img width="1280" alt="image" src="https://github.com/user-attachments/assets/b6243957-99fa-452d-9e03-eaa131b50dc3">
<img width="1280" alt="image" src="https://github.com/user-attachments/assets/875f35b7-db52-4d2a-a117-ee4f7cce50da">

## 主要功能

### 1. 钱包管理 (Wallet Manager)
- **批量创建钱包**
  - 支持一次性创建最多200个钱包(已完成)
  - 自动生成公私钥对(已完成)
  - 实时显示SOL余额(已完成)

- **钱包分组管理** 
  - 支持Dev、底仓、刷单、刷量等分组(已完成)
  - Dev组限制单一钱包(已完成)
  - 灵活的分组调整(已完成)

- **批量转账功能**
  - 支持从Dev钱包批量分发到其他组(已完成)
  - 支持从其他组批量归集到Dev钱包(已完成)
  - 自动计算gas费，确保转账成功(已完成)
  - 实时显示转账进度和结果(已完成)

- **导入导出功能**
  - 支持批量导入Base58格式私钥(已完成)
  - 支持按组导出钱包信息为CSV(已完成)
  - 导入时自动验证私钥格式(已完成)

### 2. 虚拟地址生成
- **多线程并行计算**
  - 自动使用多CPU核心(已完成)
  - 实时显示生成速度(已完成)
  - 支持自定义后缀(已完成)

- **性能优化**
  - 批量生成和验证(已完成)
  - 内存使用优化(已完成)
  - 支持取消生成(已完成)

### 3. PumpFun功能
- **代币监控**
  - 支持山丘之王(KOTH)模式
  - 支持随机仿盘模式(已完成)
  - 自动获取代币元数据(已完成)

- **交易执行**
  - 支持设置底仓买入区间
  - 自动计算最优gas费(已完成)
  - 集成Jito MEV保护(已完成)
  - 交易结果实时反馈(已完成)
  - 一键卖出、刷量、砸盘、拉盘(待完成)



## 技术栈
- Next.js 12.3.4
- React 18.2.0
- Chakra UI
- SQLite3
- Solana Web3.js
- Web Workers

## 安装部署

1. 克隆项目
```bash
git clone https://github.com/vnxfsc/Pump_tools_bak.git
cd Pump_tools_bak
```

2. 安装依赖
```bash
npm install
```

3. 运行开发环境
```bash
npm run dev
```

4. 构建生产环境
```bash
npm run build
npm start
```

## 项目结构
```
solana-tools/
├── components/          # React组件
├── lib/                # 工具类和数据库操作
│   ├── KOTH.js        # 山丘之王相关
│   ├── NEW.js         # 新代币相关
│   ├── db.js          # 数据库操作
│   ├── tradeHandler.js # 交易处理
│   ├── vanityAddress.js # 虚拟地址生成
│   └── vanityWorker.js  # Web Worker实现
├── pages/              # 页面和API路由
│   ├── api/           # API接口
│   ├── _app.js        # Next.js入口
│   ├── index.js       # 首页
│   ├── pump-fun.js    # PumpFun功能页
│   └── wallet-manager.js # 钱包管理页
└── public/            # 静态资源
```

## 注意事项

1. **私钥安全**
- 所有私钥均使用SQLite本地存储
- 请勿将包含真实资金的私钥导入测试环境
- 建议定期备份数据库文件

2. **性能考虑**
- 虚拟地址生成可能需要较长时间
- 建议限制同时运行的Worker数量
- 注意监控系统资源使用

3. **API限制**
- 注意RPC调用频率限制
- 建议使用付费节点以提高稳定性
## 更新日志
- 2024-11-16
  - **钱包管理优化**
    - 移除了底仓钱包数量限制，现在支持任意数量的底仓钱包
    - 优化了钱包余额检查，使用数据库缓存而不是RPC请求
  - **交易功能优化**
    - 实现了多组交易功能，每组最多5个钱包
    - 第一组固定为1 Dev + 4 底仓，后续组每组5个底仓
    - 添加了交易分组显示和日志
    - 优化了交易延迟时间（改为100ms）
  - **卖出功能完善**
    - 移除了卖出时的余额检查（因为手续费很小）
    - 修复了卖出交易参数格式
    - 保持和买入相同的分组逻辑
  - **日志系统优化**
    - 固定了日志区域大小
    - 优化了日志显示效果
    - 移除了重复的日志输出
    - 添加了更详细的交易信息显示
  - **状态管理优化**
    - 添加了页面状态的本地存储
    - 优化了状态恢复逻辑
    - 修复了页面切换导致数据丢失的问题
  - **API优化**
    - 调整了KOTH元数据API
    - 简化了API请求逻辑
    - 优化了错误处理
  - **其他改进**
    - 修复了一些UI布局问题
    - 优化了错误提示
    - 改进了代码结构

## 参与贡献
欢迎提交 Pull Request 或提出 Issue。

## 问题反馈
如果你发现了bug或有新功能建议，请提交 Issue。

## 更新计划
我们会定期更新项目进展，请关注项目动态。每个重要功能完成后都会发布新版本。
