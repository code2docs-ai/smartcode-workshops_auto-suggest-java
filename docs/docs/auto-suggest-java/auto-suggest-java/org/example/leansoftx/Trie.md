# 基础信息

|      |      |
|------|------|
| 编码语言 | .java |
| 代码路径 | auto-suggest-java/src/main/java/org/example/leansoftx/Trie.java |
| 包名 | org.example.leansoftx |
| 依赖项 | ['java.util'] |
| 概述说明 | 该类实现了 Trie 数据结构，提供插入单词、自动补全、获取所有单词、打印 Trie 结构和拼写建议等功能。插入和自动补全使用前缀查询，拼写建议基于 Levenshtein 距离算法。 |

# 说明

这个类是一个实现了 Trie（字典树）数据结构的类，它提供了插入单词、自动补全、获取所有单词、打印 Trie 结构和拼写建议的功能。

首先，插入单词功能允许用户将一个单词插入到 Trie 中。插入过程会按照单词中的每个字母逐级插入，并最终在 Trie 的最后一个节点中添加一个结束标记，以标识单词的结束。

其次，自动补全功能基于前缀查询。用户可以输入一个前缀，然后程序会找到 Trie 中以该前缀开头的所有单词，并返回给用户。这个功能可以帮助用户在输入过程中快速找到可能的单词选项。

第三，获取所有单词功能可以返回 Trie 中的所有存储的单词。它会遍历 Trie 的所有节点，并将所有以结束标记结尾的路径对应的单词收集起来返回。

另外，打印 Trie 结构功能可以以可读性良好的形式打印出 Trie 数据结构的结构，以帮助用户理解 Trie 的组织和存储方式。

最后，拼写建议功能基于 Levenshtein 距离算法。用户可以输入一个单词，然后程序会根据该单词与 Trie 中存储的单词之间的 Levenshtein 距离，给出一些建议的拼写修改。这个功能可以帮助用户在拼写错误时找到正确的拼写。

通过这个类，用户可以方便地进行单词的插入、查询和自动补全，并且可以获取到 Trie 数据结构的完整信息以及一些建议的拼写修改。这对于需要处理大量单词或需要快速搜索和修改单词的应用场景十分实用。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| Trie | class | 这个信息是关于一个实现了 Trie 数据结构的类。包含了插入单词、自动补全、获取所有单词、打印 Trie 结构和拼写建议的功能。插入单词和自动补全是基于前缀查询。拼写建议是基于 Levenshtein 距离算法。 |



## 类 Trie

|      |      |
|------|------|
| 访问范围 | public |
| 类型 | class |
| 名称 | Trie |
| 说明 | 这个信息是关于一个实现了 Trie 数据结构的类。包含了插入单词、自动补全、获取所有单词、打印 Trie 结构和拼写建议的功能。插入单词和自动补全是基于前缀查询。拼写建议是基于 Levenshtein 距离算法。 |


### UML类图

classDiagram
class TrieNode {
  - children: Map<Character, TrieNode>
  - value: char
  - isEndOfWord: boolean
  + TrieNode()
  + TrieNode(char value)
  + hasChild(char c): boolean
}

class Trie {
  - root: TrieNode
  + Trie()
  + insert(word: String): boolean
  + autoSuggest(prefix: String): List<String>
  + getAllWordsWithPrefix(node: TrieNode, prefix: String): List<String>
  + getAllWords(): List<String>
  + printTrieStructure(): void
  - _printTrieNodes(root: TrieNode, format: String, isLastChild: boolean): void
  + getSpellingSuggestions(word: String): List<String>
  + levenshteinDistance(s: String, t: String): int
}

Trie "1" --|> TrieNode
Trie "1" ..> "1" TrieNode : root
Trie "1" --|> "" {
  + insert(word: String): boolean
  + autoSuggest(prefix: String): List<String>
  + getAllWordsWithPrefix(node: TrieNode, prefix: String): List<String>
  + getAllWords(): List<String>
  + printTrieStructure(): void
  + getSpellingSuggestions(word: String): List<String>
  + levenshteinDistance(s: String, t: String): int
}

interface "" {
  + insert(word: String): boolean
  + autoSuggest(prefix: String): List<String>
  + getAllWordsWithPrefix(node: TrieNode, prefix: String): List<String>
  + getAllWords(): List<String>
  + printTrieStructure(): void
  + getSpellingSuggestions(word: String): List<String>
  + levenshteinDistance(s: String, t: String): int
}

legend
  Trie: 根据给定的字符串构建的前缀树，用于快速插入、查询和自动补全单词。
  TrieNode: Trie的节点，包含子节点、值和是否是单词结尾的标志。
  insert(word): 向Trie中插入一个单词，返回插入结果。
  autoSuggest(prefix): 根据给定的前缀，在Trie中查找所有可能的单词。
  getAllWordsWithPrefix(node, prefix): 获取以给定节点为根的子树中的所有单词。
  getAllWords(): 获取Trie中的所有单词。
  printTrieStructure(): 输出Trie的结构。
  getSpellingSuggestions(word): 根据给定的单词，在Trie中查找可能的拼写建议。
  levenshteinDistance(s, t): 计算两个字符串之间的Levenshtein距离。
end legend


### 内部方法调用关系图

graph TD;
    Trie --> insert
    Trie --> autoSuggest
    Trie --> getAllWords
    Trie --> printTrieStructure
    Trie --> getSpellingSuggestions
    insert --> getAllWordsWithPrefix
    autoSuggest --> getAllWordsWithPrefix
    getAllWordsWithPrefix --> null
    printTrieStructure --> _printTrieNodes
    getSpellingSuggestions --> levenshteinDistance
    levenshteinDistance -.-> Math.min
    levenshteinDistance -.-> Math.min
    levenshteinDistance -.-> Math.min

类Trie是一个前缀树的数据结构，用于存储和检索字符串。插入函数insert用于将一个字符串插入到前缀树中，自动建议函数autoSuggest根据给定的前缀返回以该前缀开头的字符串列表，获取以某个节点为根的所有以某个前缀开头的字符串列表的函数getAllWordsWithPrefix目前为null，获取所有字符串的函数getAllWords调用getAllWordsWithPrefix函数，打印前缀树的函数printTrieStructure和获取拼写建议的函数getSpellingSuggestions，它根据给定的单词返回与该单词距离不超过2的字符串列表。其中，拼写距离计算函数levenshteinDistance使用动态规划的方法计算两个字符串之间的编辑距离。


### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| root | TrieNode | 包含一个私有的root节点的Trie树。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| getAllWordsWithPrefix | List<String> | 给定一个前缀和一个TrieNode节点，返回包含该前缀的所有单词列表。 |
| _printTrieNodes | void | 根据提供代码，逐层打印Trie树节点，按层级排列，每层按照字母顺序排序。 |
| printTrieStructure | void | printTrieStructure方法用于打印Trie（字典树）结构。首先打印根节点"root"，然后调用_printTrieNodes方法递归打印所有节点。 |
| insert | boolean | 插入函数用于将单词插入字典树中，如果单词已存在则返回false，否则返回true。函数通过遍历单词的每个字符，检查当前字符是否存在子节点，如果不存在则创建新的节点。最后标记最后一个字符节点为单词的结束节点。 |
| getAllWords | List<String> | 该方法返回一个列表，列表中包含了以指定前缀开头的所有单词。 |
| getSpellingSuggestions | List<String> | 根据提供的单词，生成一个拼写建议的列表。获取以单词首字母为前缀的所有单词，通过计算与给定单词的编辑距离，将距离不超过2的单词加入建议列表，并返回。 |
| autoSuggest | List<String> | 该代码提供了一个名为`autoSuggest`的方法，该方法接受一个字符串参数`prefix`。方法首先创建一个`TrieNode`类型的变量`currentNode`，初始值为根节点。然后，遍历`prefix`字符串的每个字符，检查当前节点是否有对应字符的子节点。如果没有子节点，则返回一个空的列表。如果有子节点，将`currentNode`更新为对应子节点。最后，调用`getAllWordsWithPrefix`方法，返回以`currentNode`为根节点的树中以`prefix`为前缀的所有单词。 |
| levenshteinDistance | int | 该方法用于计算两个字符串之间的Levenshtein距离。Levenshtein距离是指将一个字符串转换成另一个字符串所需的最小编辑操作次数。编辑操作包括插入、删除和替换字符。方法中使用动态规划来计算距离，通过填充一个二维数组来记录每个子问题的解。最终返回数组的最后一个元素，即最小距离。 |




