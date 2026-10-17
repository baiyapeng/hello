# hello

一个简洁的 Go 项目模板，展示标准的 Go 项目布局（`cmd/` + `internal/`），
可作为新项目的脚手架快速起步。

## 项目结构

```text
hello/
├── cmd/
│   └── hello/
│       └── main.go        # 程序入口
├── internal/
│   └── greeter/
│       └── greeter.go     # 问候逻辑（仅限本项目内部引用）
├── go.mod                 # 模块定义：neo.com/hello
├── go.sum
├── LICENSE                # MIT 开源协议
└── README.md
```

## 环境要求

- Go 1.27.1+

## 快速开始

```bash
# 克隆仓库
git clone git@github.com:baiyapeng/hello.git
cd hello

# 直接运行
go run ./cmd/hello
# 输出: Hello, Gopher
```

## 构建与测试

```bash
# 编译二进制（输出到 bin/）
go build -o bin/hello ./cmd/hello

# 运行测试
go test ./...
```

## 使用 greeter 包

`internal/greeter` 提供 `Hello` 函数：

```go
package greeter

func Hello(name string) string {
	return "Hello, " + name
}
```

由于包位于 `internal/` 下，仅本模块内的代码可以导入它。

## 开源协议

本项目基于 [MIT License](LICENSE) 开源，可自由用于学习与商业用途。
