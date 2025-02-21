# 基础信息

|      |      |
|------|------|
| 编码语言 | .java |
| 代码路径 | auto-suggest-java/src/main/java/org/example/leansoftx |
| 包名 | org.example.leansoftx |
| 概述说明 | 该程序是一个帮助用户操作Trie数据结构的工具，提供搜索单词、前缀自动补全、删除单词和获取拼写建议等功能。通过调用Trie类中的方法，用户可以对单词进行查找和处理。TrieNode类是用于构建字典树节点的类，具有children、isEndOfWord和value属性，可以实现字典树的插入、查找和删除等操作。目前程序功能还未完全实现。 |

# 说明

Trie类是实现前缀树数据结构的类，可以插入单词、自动补全、打印树结构和拼写建议。其中，getAllWordsWithPrefix方法返回指定前缀的所有单词集合；getSpellingSuggestions方法返回与给定单词在相似度2以内的所有单词建议。Trie类能够实现单词的查找和处理。

TrieNode类是实现字典树的节点类，具有children属性存储子节点信息，通过hasChild方法判断是否存在指定子节点。还有isEndOfWord属性表示当前节点是否为单词的末尾，value属性存储节点的值。TrieNode类构建和表示字典树的节点结构。字典树是一种高效存储和检索字符串的数据结构，广泛应用于文本搜索和字典应用。使用TrieNode类可以创建完整的字典树，插入、查找和删除字符串。例如，通过调用hasChild方法判断字符串在字典树中是否存在。isEndOfWord属性用于标记字典树中节点是否为完整的单词。value属性用于存储节点的值，如单词的含义或解释。TrieNode类提供构建字典树的基本功能和属性，支持高效操作和查询。

该程序是操作Trie数据结构的工具，提供搜索单词、前缀自动补全、删除单词和获取拼写建议等功能。用户通过控制台输入指令使用功能。目前具体功能尚未实现。


### 包内部结构视图

graph TD
leansoftx --> Trie
leansoftx --> TrieNode
leansoftx --> Main

描述：这是一个用于自动提示的Java代码项目。项目的主要包是`org.example.leansoftx`，其中包含了三个Java文件：`Trie.java`，`TrieNode.java`和`Main.java`。`Trie.java`文件是一个实现了Trie树数据结构的类，`TrieNode.java`文件是Trie树中的节点类，`Main.java`文件是项目的入口类。这个图形清晰地展示了这些文件与文件夹之间的层级关系。

# 文件列表 File List

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| [Main.java](Main.md) | file | 这是一个帮助操作Trie数据结构的工具，可以搜索单词、自动补全、删除和获取拼写建议。指令通过控制台输入。具体功能未实现。 |
| [TrieNode.java](TrieNode.md) | file | TrieNode类是用于实现字典树的节点类。具有children属性，判断是否存在子节点。还有isEndOfWord属性表示节点是否为单词末尾，value属性用于存储节点值。 |
| [Trie.java](Trie.md) | file | Trie类实现前缀树，支持插入、补全、打印树、拼写建议等功能。getAllWordsWithPrefix方法返回指定前缀的所有单词，getSpellingSuggestions返回相似度为2以内的单词。 |


