# PumpFun Tools - PumpFun工具集

一个功能强大的PumpFun工具集合，包含钱包管理、虚拟地址生成和交易执行等功能。

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
cd solana-tools
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

## 许可证
MIT License

## 更新日志

### v0.1.0 (2024-11-10)
- 初始版本发布
- 实现基础钱包管理功能
- 添加虚拟地址生成功能
- 支持批量转账操作

## 未来开发计划

### 1. KOTH功能完善
- [ ] 完善山丘之王(KOTH)模式监控
  - 实现实时价格监控
  - 添加价格波动提醒
  - 优化数据获取稳定性
- [ ] 添加历史数据分析
  - 显示历史价格走势
  - 添加交易量分析
  - 支持技术指标计算

### 2. 交易功能增强
- [ ] 完善底仓买入功能
  - 添加智能分仓策略
  - 支持自定义买入时机
  - 添加风险控制机制
- [ ] 优化交易执行
  - 实现交易队列管理
  - 添加失败重试机制
  - 优化gas费估算
```

### 3. 性能优化计划
- [ ] GPU加速支持
  - 实现GPU虚拟地址生成
  - 添加WebGL计算支持
  - 优化内存使用
- [ ] 多线程优化
  - 优化Worker通信机制
  - 添加任务调度系统
  - 实现动态线程管理

### 4. 新功能规划
- [ ] 钱包监控
  - 添加余额变动提醒
  - 支持代币监控
  - 添加交易历史记录
- [ ] 自动交易
  - 添加定时交易功能
  - 支持条件触发交易
  - 实现策略自动执行
- [ ] 数据分析
  - 添加交易数据统计
  - 支持收益分析
  - 添加风险评估

### 5. UI/UX改进
- [ ] 界面优化
  - 添加深色模式
  - 优化移动端适配
  - 改进交互体验
- [ ] 功能引导
  - 添加新手引导
  - 完善错误提示
  - 添加操作教程

### 6. 安全性增强
- [ ] 私钥管理
  - 添加加密存储
  - 支持硬件钱包
  - 实现多重签名
- [ ] 交易安全
  - 添加交易确认机制
  - 实现交易限额
  - 添加异常检测

## 开发时间线

### 第一阶段 (1-2个月)
- 完善 KOTH 功能
- 优化底仓买入策略
- 实现基础监控功能

### 第二阶段 (2-3个月)
- 实现 GPU 加速
- 优化多线程性能
- 完善自动交易功能

### 第三阶段 (3-4个月)
- 实现数据分析功能
- 优化 UI/UX
- 增强安全机制

## 参与贡献
欢迎提交 Pull Request 或提出 Issue。详细贡献指南请参考 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 问题反馈
如果你发现了bug或有新功能建议，请提交 Issue。

## 更新计划
我们会定期更新项目进展，请关注项目动态。每个重要功能完成后都会发布新版本。