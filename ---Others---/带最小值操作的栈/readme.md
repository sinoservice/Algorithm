﻿## 带最小值操作的栈

实现一个带有取最小值min方法的栈，min方法将返回当前栈中的最小值。
你实现的栈将支持push，pop 和 min 操作，所有操作要求都在O(1)时间内完成。

```
注意事项 
如果堆栈中没有数字则不能进行min方法的调用
```

样例 

如下操作：push(1)，pop()，push(2)，push(3)，min()， push(1)，min() 返回 1，2，1

问题：

调用min()函数的时候，返回当前stack里面的最小值，如果当前stack里面的最小值被pop掉，那么这时候，如何寻找最小值？


思路：
创建两个栈，分别是numstack和ministack。
numstack用来正常的push和pop元素，
ministack的作用是来记录当前栈里面的最小值。
这两个栈的大小是一样的，每一个是一一对应。


在push的时候，如何当前元素小于ministack的栈顶元素，那么这个表示栈里面又来了一个更小的元素，所以，要把它加入栈顶。

如果当前元素大于ministack的栈顶元素，那么表示来了一个更大的元素，那么这个时候栈里面的最小的元素依然是ministack的原来的栈顶元素，所以就要ministack里面原来的栈顶元素再push一次。


可以看截图来参考理解一下。