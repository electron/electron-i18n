# 在 C++ 代码中使用 clang-format 工具

[`clang-format`](https://clang.llvm.org/docs/ClangFormat.html)是一个自动格式化 C/C++/Objective-C 代码的工具, 可以让开发人员不需要担心代码审查期间的样式问题.

强烈建议在发起请求之前格式化已更改的 C++ 代码，这将节省您和审阅者的时间.

你可以通过 `npm install -g clang-format` 安装 `clang-format` 和 `git-clang-format`.

To automatically format a file according to Electron C++ code style, run `clang-format -i path/to/electron/file.cc`. It should work on macOS/Linux/Windows.

格式化已更改代码的工作流:

1. 在 Electron 存储库中更改代码.
2. 运行 `git add your_changed_file.cc`.
3. 运行 `git-clang-format`, 然后你将可能会看到修改后的 `your_changed_file.cc`, 这些修改是从 `clang-format` 生成的.
4. 运行 `git add your_changed_file.cc`, 并提交你的修改.
5. 现在准备好的分支推送请求已经被打开.

If you want to format the changed code on your latest git commit (HEAD), you can run `git-clang-format HEAD~1`. See `git-clang-format -h` for more details.

## 编辑器集成

You can also integrate `clang-format` directly into your favorite editors. For further guidance on setting up editor integration, see these pages:

* [Atom](https://atom.io/packages/clang-format)
* [Vim & Emacs](https://clang.llvm.org/docs/ClangFormat.html#vim-integration)
* [Visual Studio Code](https://marketplace.visualstudio.com/items?itemName=xaver.clang-format)
