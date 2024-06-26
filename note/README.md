# raft-rs 阅读笔记

代码目录树
```shell
tree src/

src
├── confchange
│   ├── changer.rs
│   ├── datadriven_test.rs
│   ├── restore.rs
│   └── testdata: 测试数据
│       └── ...
├── confchange.rs
├── config.rs
├── errors.rs
├── lib.rs
├── log_unstable.rs
├── quorum
│   ├── datadriven_test.rs
│   ├── joint.rs
│   ├── majority.rs
│   └── testdata: 测试数据
│       └── ...
├── quorum.rs
├── raft.rs: 最重要的文件
├── raft_log.rs
├── raw_node.rs
├── read_only.rs
├── status.rs
├── storage.rs: 定义了 Storage 接口并实现了用于测试的 MemStorage struct
├── tracker
│   ├── inflights.rs
│   ├── progress.rs
│   └── state.rs
├── tracker.rs
└── util.rs
```


运行
```shell
cargo run --example single_mem_node
cargo run --example five_mem_node
```


# 主流程分析

