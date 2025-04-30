# uv -- 最强Python项目管理工具


## 简介

作为著名的调包语言，python的包管理/依赖安装一直是一个糟心的事情，特别是现在系统级的包管理器均拒绝pip全局安装，使用虚拟环境是唯一之举。

在接触uv之前，我通常使用python自带的venv来创建、管理虚拟环境，有时候一些特殊的包需要借助conda来处理。和正常使用pip没啥区别，激活个环境就正常用。但是直到上个月我第一次使用uv，立刻就爱上这个工具。因为它实在是太快了！这个快不仅仅是下载速度，而是复现项目、环境配置的快，有种最开始使用docker的感觉。

这里仅记录一些基本的使用，只要用上一两次就能感受到这个工具的便捷与强大。

## 管理自己的项目

基本流程大概是：

创建项目文件夹、创建需要的虚拟环境、安装依赖、跑码。
```shell
uv init <name-of-project> 
cd <name-of-project>
uv sync
uv add numpy ...
uv run main.py
```

如需指定python版本
```shell
uv python list # 查看已有的pythn解释器
uv python install 3.10 3.11 3.12 3.13
uv venv --python 3.12 # 记得把两个配置文件里的版本改对应
...
```

设置镜像
```shell
vim pyproject.toml
>> [[uv.tool.index]]
>> url = "https://mirrors.tuna.tsinghua.edu.cn/pypi/web/simple"
>> default = true
```

## 复现项目
```shell
# uv管理的项目
uv sync
# 其他
uv pip sync requirements.txt
```

## Tips

1. 无前缀执行

uv和通常的虚拟环境不太一样，执行前需要 `uv run`, 一些依赖二进制工具的项目可能因此无法启动, 只需要和一般的虚拟环境一样激活一下就行了。

---

> 作者: luoluo  
> URL: https://luoluokong10.github.io/2025/04/uv/  

