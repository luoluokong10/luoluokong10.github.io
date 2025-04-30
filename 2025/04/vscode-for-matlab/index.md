# VSCode for Matlab


## 简介

Matlab 本身非常好用，但是补全是在是太逆天了，也没法很轻松的使用snippet和配置UI，借助第三方的编辑器可以一定程度上解决这些问题。

工具上，我考虑了 `Jupyterlab` 和 `VSCode`. 实操下来官方的 `jupyter-matlab-proxy` 在我这台 m2 上总是连接不上，开不了端口，但是单独使用matlab的工具又能正常开webui，看了几个issue也没啥帮助先搁置了。目前只能用 `VSCode`了。(neovim 和 emacs 好像也都可以，但是我看社区评价不咋滴，而且用这俩写matlab有点emmm)

原理都是通过 Python 调用 matlab 引擎，让 Python 执行 matlab 程序。其实上直接命令行也能执行，但是还要分情况考虑带不带jvm，不同系统还不一样，算了吧。

## 配置
> 需要 python3.9 - 3.11 matlab 2024b 最高支持到 3.11
1. VSCode 上

`VSCode` 安装插件包 `Matlab Extension Pack`
配置文件写入
```json
{
    // "MATLAB.showFeatureNotAvailableError": false,
    "files.associations": {"*.m": "matlab"},
    "matlab.mlintpath": "/Applications/MATLAB_R2024b.app/bin/maca64/mlint",
    "matlab.linterEncoding": "utf8",
    "matlab.matlabpath": "/Applications/MATLAB_R2024b.app/bin/matlab",
    "matlab-interactive-terminal.pythonPath": "/opt/homebrew/bin/python3.10",
    "matlab-interactive-terminal.unicodeSwitch": true,
}
```
覆盖掉原本的 `F5` 快捷键 -> .../Code/User/keybindings.json
```json
[
    {
        "key": "Cmd+r",
        "command": "matlab.runFile",
        "when": "editorTextFocus && !findInputFocussed && !matlab.isDebugging && !replaceInputFocussed && editorLangId == 'matlab' && resourceScheme != 'untitled'"
        
    },
]
```

2. Matlab 上
```shell
which matlab # 记得加PATH
cd ...\extern\engines\python # Matalb 目录下
python setup.py install
# python版本 3.9 - 3.11 需要 setuptools 可以弄个虚拟环境激活
```

---

> 作者: luoluo  
> URL: https://luoluokong10.github.io/2025/04/vscode-for-matlab/  

