## 👋 Hello world
让我们来写第一个程序吧, Hello World C3版:

```c3
import std::io;

fn void main()
{
    io::printn("Hello, World!");
}
```

[`import`](/language-fundamentals/modules/#importing-modules) 语句倒入了一个模块, 同时我们想要的函数 `printn` 就在
模块 `std::io` 里.

然后我们通过 `fn` 关键字和后置的返回值类型定义了一个 [函数](/language-fundamentals/functions/). 我们什么都不需要返回, 所以使用 `void` 类型. 叫做 `main` 的函数后跟随者它的参数列表, (虽然是空的).
```c3
fn void main() {}
```

注:
`main` 函数是特殊的, 它是程序的开始或者入口点

UnixLike系统中我们可以加入一些特定的参数, 如定义 `fn void main(String[] args)`. 这样 "args" 包含了尾随在程序后的传参的 [切片](/language-common/arrays/#slice), starting 

### 🔭 函数作用域
`{` 和 `}` 标志着函数定义的开始和结束, 
我们称之为作用域

### 📏 导入可以使用简写形式

如果需要, 我们本可以使用原始的完整路径 `std::io::printn`, 但我们可以将其缩短为只包含最底层模块的形式, 例如 `io::printn` 这是 C3 中的“惯例”, 被称为“路径缩短”, 它可以避免编写过长的导入路径, 使代码更难阅读

```diff lang="cpp"
- std::io::printn("Hello, World!");
+ io::printn("Hello, World!");
```

`io::printn` 函数接受一个参数，将其打印出来，并跟一个换行符，然后函数结束，程序终止。

## 🔧 编译

我们把上述的代码放到 `hello_world.c3` 里!

我们就可以:
```bash 
c3c compile hello_world.c3
```

然后:
```bash
./hello_world
```

它应该会打印 `Hello, World!` 然后把你带回repl. 
如果你是win用户, 那么你会得到 `hello_world.exe`. 同样的方式调用它, 你也会得到同样的结果

### 🏃 编译并直接运行

当你懒得输入两个命令时. 那就直接 `compile-run` 吧:

```bash {4}
$ c3c compile-run hello_world.c3
> 编译出来 'hello_world'.
> 启动了 hello_world...
> Hello, World
```

想了解更多编译选项? [检查编译选项](/build-your-project/build-commands/).
### 🎉 能正常工作! 
恭喜你, 你成功运行了一个C3程序

### ❓ 有问题!!!
欢迎来到 [C3 Discord](https://discord.gg/qN76R87).
