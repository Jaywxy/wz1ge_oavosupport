# 前言

​为了尽量减少沟通上的障碍，特此编写本文档  
​远程面试助攻， 通过语音转达，音频转接等技术，帮你收获**国内外大厂名企offer** 
VO面试中，我能够帮忙解答coding问题，部分八股文问题，基础知识问题，能够非常快速的帮你响应助攻完成整个面试。而面试中的BQ问题，项目细节问题，简历问题，我需要在面试之前确定和准备。我可以使面试官无法听见我的声音，但是们和您都能听到面试官的声音，这样我就可以实现协助您完成整个面试，我提供了全套的面试工具支持，设备安装非常简单，只需在宿舍环境即可实现。确定合作之后，我们会安排时间一起调试，确保在VO过程中不会出现任何问题

I will use Voov and Pad to assist you during the interview. I will guide you through mock sessions and device setup to ensure everything runs smoothly. I specialize in Java, Python, and C++. For all VO interviews, you must schedule with me before booking with HR. I will provide you with my available time slots for you to share with HR. Payment is only required after successfully passing the VO—if it's not fully AC, there’s no charge. For more details, feel free to contact me.
# 语言

我擅长的语言是`Java`、`C++`和`Python`，你可以从中选一门语言让我作答。但是，根据题目的一些特殊性质，我可能会请求你更换语言编写。比如以下原因：

1. 一些数据结构上的性能开销，`Python`比`C++`慢得多，这时如果我发现这道题使用`Python`有超时（时间超限，Time Limited Exceed）的风险，我会告诉你我**建议**选择`C++`解答。
2. 一些题目处理输入输出比较麻烦，这时我会告诉你我**建议**选择`Python`解答。

# 面试进行前

## 预约

一定要**先和我预约时间**再和hr约时间，只需要**发我vo的时间范围**，比如1号-10号，我会根据我的schedule发给你可预约的时间，你在发给hr，**确认后第一时间**告诉我即可。

## 选定代码共享的方式

我将在一下3种通道之一
1.	石墨文档
2.	向日葵
3.	腾讯会议
我们会在VO开始前进行调试和mock，确保在VO过程中不会出现任何问题。

# 面试进行中

本章讲介绍面试进行中的工作，具体细节以调试为准，中英文可选。

## 题目传达

不需要你传达任何东西，只需要专注面试即可，题目我自己可以看到，整个过程会非常轻松，只需要按照我的步骤和流程来即可。具体方式方法和步骤我们在调试的时候会过一遍，确保你完全熟悉。  


## 回复

在专属的通道上回复，我会分为如下的几个步骤（假设使用的语言是`Python`）。

1. 收到题目后，我首先会用简单的几句话写思路。以上面的题目为例，我会写：

```py
# 由于字符最多只有26个，因此字符串的长度至多为26。我们只需要枚举每个字符作为左端点，然后逐渐向右扩展，遇到第一个遇到过的字符停下即可。
```

2. 开始编写代码。

```py
def solve(s)
    n = len(s)
    ans = 0
    for i in range(n):
        st = set()
        for j in range(i, n):
            if s[j] in st:
                break
            st.add(s[j])
        ans = max(ans, len(st))
    return ans
```

3. 生成注释。如果生成的注释不清晰，我还会进一步修正。

```py
def solve(s):
    # 获取输入字符串的长度
    n = len(s)
    # 初始化答案为0
    ans = 0
    # 外层循环，从字符串的每一个字符开始
    for i in range(n):
        # 创建一个空集合用于存储不重复的字符
        st = set()
        # 内层循环，从当前字符开始，遍历到字符串的末尾
        for j in range(i, n):
            # 如果字符已经在集合中，结束内层循环
            if s[j] in st:
                break
            # 如果字符不在集合中，将其添加到集合
            st.add(s[j])
        # 更新答案为目前找到的最大不重复子串的长度
        ans = max(ans, len(st))
    # 返回最长无重复字符子串的长度
    return ans
```

4. 如果有样例，我会编写测试样例代码。

```py
print(solve("abcabcbb"))
print(solve("pwwkew"))
print(solve("bbbbb"))
```

因此，最终页面看起来如下：

```py
# 由于字符最多只有26个，因此字符串的长度至多为26。我们只需要枚举每个字符作为左端点，然后逐渐向右扩展，遇到第一个遇到过的字符停下即可。

def solve(s):
    # 获取输入字符串的长度
    n = len(s)
    # 初始化答案为0
    ans = 0
    # 外层循环，从字符串的每一个字符开始
    for i in range(n):
        # 创建一个空集合用于存储不重复的字符
        st = set()
        # 内层循环，从当前字符开始，遍历到字符串的末尾
        for j in range(i, n):
            # 如果字符已经在集合中，结束内层循环
            if s[j] in st:
                break
            # 如果字符不在集合中，将其添加到集合
            st.add(s[j])
        # 更新答案为目前找到的最大不重复子串的长度
        ans = max(ans, len(st))
    # 返回最长无重复字符子串的长度
    return ans

print(solve("abcabcbb"))
print(solve("pwwkew"))
print(solve("bbbbb"))
```



如果你写错了，我会进行提醒。以上面为例，你在第7行将`s[j]`写成了`s[i]`，如下：

```py
def solve(s)
    n = len(s)
    ans = 0
    for i in range(n):
        st = set()
        for j in range(i, n):
            if s[i] in st:
                break
            st.add(s[j])
        ans = max(ans, len(st))
    return ans
```

我会这样子输入很多个字符`v`提醒你下一行有错，比如：

```py
def solve(s)
    n = len(s)
    ans = 0
    for i in range(n):
        st = set()
        for j in range(i, n):
            vvvvvvvvvvv抄错了
            if s[i] in st:
                break
            st.add(s[j])
        ans = max(ans, len(st))
    return ans
```

# 关于等待

面试官给你题目后，准备一些话术，思考两分钟，可以读读题。两分钟内，我会把你需要和面试官交流的内容打出来，直接读即可。所有流程我们调试的时候会过一遍。 


# VO辅助价格


根据**公司定位**+**具体轮数**+**面试时间**+**市场均价**+**找我的次数** 浮动在$0 - $2800之间
