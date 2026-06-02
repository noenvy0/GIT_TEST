# 项目说明

## 项目概览

这是一个用于练习或验证基础 C 开发流程的最小控制台项目。项目目前没有第三方依赖、构建系统或自动化测试框架。

程序入口位于 `main.c`。当前源码会向标准输出打印两次：

```text
hello world
hello world
```

## 目录结构

```text
.
├── .vscode/
│   └── c_cpp_properties.json  # VS Code C/C++ 扩展配置
├── output/                    # 当前为空，可能预留给构建产物
├── hello.exe                  # 已提交的 Windows 可执行文件
└── main.c                     # 程序源码和 main 函数
```

## 开发环境

- 语言：C
- 目标平台：Windows
- 编译器：MinGW-w64 GCC
- VS Code IntelliSense 模式：`gcc-x64`
- VS Code 配置中的编译器路径：`D:\Software\gcc\Install\mingw64\bin\gcc.exe`
- 头文件搜索范围：`${workspaceFolder}/**`
- 预定义宏：`_DEBUG`、`UNICODE`、`_UNICODE`

## 构建与运行

项目尚未提供 `Makefile`、CMake 配置或 VS Code 构建任务。可以在仓库根目录使用 GCC 手动构建：

```powershell
gcc main.c -o hello.exe
.\hello.exe
```

如需将产物放入预留目录，可以使用：

```powershell
gcc main.c -o output\hello.exe
.\output\hello.exe
```

## 当前行为与注意事项

- `main.c` 当前包含两个相同的 `printf("hello world\n");` 调用。
- 仓库根目录中现有的 `hello.exe` 运行时只输出一次 `hello world`，与当前源码不一致。修改源码后应重新编译，不要把现有二进制文件视为最新行为。
- `hello.exe` 已被 Git 跟踪。更新源码后，是否同步提交编译产物应根据任务要求决定，避免无意义的二进制变更。
- `output/` 当前为空，且空目录不会被 Git 跟踪。
- 项目目前没有自动化测试。最基本的验证方式是编译成功并运行程序，检查标准输出。

## 修改建议

- 保持实现简单，优先直接修改 `main.c`。
- 新增多个源码文件时，再考虑引入 `Makefile` 或 CMake。
- 提交前至少执行一次编译和运行验证。
- 若新增测试、构建脚本或目录约定，请同步更新本文档。
