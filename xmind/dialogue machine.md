http://www.sohu.com/a/218382703_473283
非任务导向型对话系统：
目前用的主要是两种方法
1.生成方法 例如序列到序列模型
在对话过程中产生合适的回复，生成型聊天机器人是目前研究界的一个热点，和检索型机器人不同的是它可以生成一种全新的回复，因此相对更为灵活，但它有自身的缺点，比如会出现语法错误，或者生成一些没有意义的回复。
2.基于检索的方法
从事先定义好的索引中进行搜索，学习从当前对话中选择回复，检索行方法的缺点在于它过于依赖数据质量，如果选用的数据质量欠佳，很有可能前功尽弃。
任务导向型系统
1.管道方法
任务导向型对话系统包括四个关键组成部分：
1）自然语言理解(NLU) 它将用户输入解析为预定义的语义槽
如果有一个话语，自然语言理解将其映射为语义槽，插槽是根据不同的场景预先定义的
话语层次类别 如用户的意图和话语类别 
另一个是字级信息提取，如命名实体识别和槽填充
对话意图检测是为了检测用户的意图，它将话语划分为一个预先定义的意图

2）对话状态跟踪 对话状态跟踪是确保对话系统健壮性的核心组件，它在对话的每一轮次对用户的目标进行预估，
管理每个回合的输入和对话历史，输出当前对话状态，这种典型的状态结构通常称为槽填充和语义框架
传统的方法发已经在大多数商业实现中得到了广泛应用，通常采用手工规则选择最有可能的输出结果，基于规则的系统最用以出现频繁错误


使用一个滑动窗口输出任意数量的可能值的概率分布序列
此处运用最多的模型是NBT

3)对话策略学习

根据状态跟踪器的状态表示，策略学习是生成下一个可用的系统操作。无论是监督学习还是强化学习都可以用来优化政策学习。监督学习是针对规则产生的行为进行的，在在线购物场景中，
如果对话状态是“推荐”，那么触发“推荐”操作，系统将从产品数据库中检索产品。强化学习方法的引入可以对对话策略进行进一步的训练，以引导系统制定最终的策略。在实际实验中，
强化学习方法的效果超过了基于规则和监督的方法。

4）自然语言生成 
一个好的生成器通常依赖于几个因素:适当性、流畅性、可读性和变化性。传统的NLG方法通常是执行句子计划。
它将输入语义符号映射到代表话语的中介形式，如树状或模板结构，然后通过表面实现将中间结构转换为最终响应。
深度学习比较成熟的方法是基于LSTM的encoder-decoder形式，将问题信息、语义槽值和对话行为类型结合起来生成正确的答案。
同时利用了注意力机制来处理对解码器当前解码状态的关键信息，
根据不同的行为类型生成不同的回复

2.端到端方法

将对话系统的学习作为学习从对话历史到系统回复的映射问题，
并应用encoder-decoder模型来训练。
然而，该系统是在监督的方式下进行训练——不仅需要大量的训练数据，而且由于缺乏对训练数据对话控制的进一步探索，
它也可能无法找到一个好的策略。

非任务导向型系统
 1.聊天机器人是通过生成方法或基于检索的方法实现的
 
 生成模型能够生成更合适的回复，而这些回复可能从来没有出现在语料库中，而基于检索的模型具有信息充裕和相应流程的优势
 1.神经生成模型
 