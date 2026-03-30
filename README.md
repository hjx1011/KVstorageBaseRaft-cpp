# KVstorageBaseRaft-cpp

基于 Raft 共识算法实现的分布式强一致性 KV 存储引擎。

## 🚀 项目特性
- **核心算法**：完整实现 Raft 协议（Leader 选举、日志复制、安全性保证）。
- **网络架构**：基于 TCP Socket 手搓轻量级 RPC 框架，支持多节点跨进程通信。
- **存储优化**：实现日志压缩（Log Compaction）与快照（Snapshot）机制，解决日志无限增长问题。
- **持久化**：基于 WAL 思想实现核心状态落盘，支持断电恢复与状态机重放。
- **高并发**：多线程并发模型，细粒度锁优化。

## 🛠️ 编译运行
```bash
mkdir build && cd build
cmake ..
make
# 启动三个节点（分别在三个终端）
./my_server 0
./my_server 1
./my_server 2