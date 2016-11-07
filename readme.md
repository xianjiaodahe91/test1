# Emacs Lisp 练习

本教程取自网络，主要目的在于本人练习`Emacs Lisp`和`Git`的基本语法。

若侵权，则马上删除，链接随后添加。


## 符号表达式
Emacs Lisp 由符号表达式构成。类似于之前学习过的`Scheme`语言*(本来就是同一种语言的不同方言)* 。如下所示：
```
(+ 2 2)
```
在Emacs的`Lisp interaction mode`模式中，把光标移动到小括号后，按下`ctrl+j`键*(以后简写为`C-j`)* 。则Emacs会计算符号表达式，并把计算结果插入到当前*buffer*中。若按下组合件`C-x C-e`，则会在Emacs的最底部显示计算结果，也就是被称为*minibuffer*的区域。类似的符号表达式示例如下：

```
(+ 2 (+ 1 1))
(+ (+ 1 2) (+ 3 4))
```

## 赋值语句
`setq`可以将一个值赋给一个变量，例如：
```
(setq my-name "Petter")
```
按下`C-x C-e`，在 *minibuffer* 中显示 Petter ，同时变量名 my-name 被赋值为 Petter 。

## 插入函数
```
(insert "Hello" " World!")
```
将 Hello World 插入到 *buffer* 中。

也可以用变量名来代替字符串，例如：
```
(insert "Hello, I am " my-name)
```
按下`C-x C-e`将在 *buffer* 中插入 Hello, I am Peter 。

## 定义函数
```
(defun hello (name) (insert "Hello " name))
```
按下`C-x C-e`，在 *minibuffer* 中显示 hello ，同时一个名为 **hello** 的函数被定义。

现在来调用这个函数，并将 "you" 作为参数传递。
```
(hello "you")
```
按下`C-x C-e`，在 *buffer* 中插入 Hello you 。

## 新建一个Buffer
下面新建一个名为 \*test\* 的 Buffer ：
```
(switch-to-buffer-other-window "*test*")
```
按下`C-x C-e`，这是屏幕上会出现两个窗口，而光标此时位于新建立的名为 \*test\* 的 *buffer* 中。
