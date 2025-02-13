# 基础信息

|      |      |
|------|------|
| 编码语言 | .java |
| 代码路径 | auto-suggest-java/src/main/java/org/example/leansoftx |
| 包名 | org.example.leansoftx |
| 概述说明 | TrieNode是一个用于存储Trie树节点的Java类，它通过Map对象维护了一个子节点集合，并提供了判断是否存在指定字符子节点的方法。这个程序实现了使用Trie树的字典，提供了搜索单词、自动补全前缀、删除单词、获取拼写建议等功能。用户可以通过控制台输入与程序交互。这个类可以方便地插入、查询、自动补全单词，并提供了完整的Trie结构信息和拼写建议功能。对于处理大量单词或快速搜索、修改单词的情况非常实用。 |

# 说明

TrieNode is a Java class used to store nodes in a Trie tree. It includes a Map object called "children" to store the children nodes of the current node. Additionally, it has a Boolean property called "isEndOfWord" to indicate if the current node is the end of a word. TrieNode can also store a character value.

The TrieNode class provides a method called "hasChild" to check if the current node has a child node with the specified character value. This method searches the Map object "children" for a mapping with the specified character as the key. If a mapping exists, it returns true, otherwise it returns false. The time complexity of this function depends on the height of the Trie tree.

In summary, TrieNode is an implementation used to store nodes in a Trie tree. It maintains a collection of child nodes using a Map object and provides methods to check for the existence of child nodes with specific characters. With the properties and methods of TrieNode, we can conveniently build and query the structure of a Trie tree.

This program is a dictionary implemented using a Trie tree. It provides the following operations: word search, prefix auto-completion, word deletion, and spelling suggestions. The program can be interacted with through the console by initializing a Trie tree and calling the relevant functions.

This class implements the Trie (also known as a prefix tree) data structure and provides functionalities for word insertion, prefix auto-completion, retrieving all words, printing the Trie structure, and spelling suggestions.

Firstly, the word insertion functionality allows users to insert a word into the Trie. The insertion process iteratively inserts each letter of the word and finally adds an end marker in the last Trie node to indicate the end of the word.

Secondly, the prefix auto-completion functionality is based on prefix search. Users can input a prefix, and the program will find all words in the Trie that start with that prefix and return them to the user. This functionality assists users in quickly finding possible word options during input.

Thirdly, the retrieve all words functionality returns all the stored words in the Trie. It traverses all nodes in the Trie and collects all words corresponding to paths that end with the end marker.

Additionally, the print Trie structure functionality prints the Trie data structure in a readable format to help users understand the organization and storage of the Trie.

Lastly, the spelling suggestions functionality is based on the Levenshtein distance algorithm. Users can input a word, and the program will suggest spelling modifications based on the Levenshtein distance between the input word and the stored words in the Trie. This functionality assists users in finding the correct spelling when making spelling mistakes.

Through this class, users can easily perform word insertion, search, and auto-completion, retrieve the complete information of the Trie data structure, and get suggested spelling modifications. This is useful for applications that deal with a large number of words or require fast word search and modification.


### 包内部结构视图

graph TD;
org.example.leansoftx --> TrieNode.java;
org.example.leansoftx --> Main.java;
org.example.leansoftx --> Trie.java;

文件和文件夹的层级关系描述：
这是一个Java项目的文件和文件夹的层级关系图。在该项目中，有一个名为`org.example.leansoftx`的文件夹，其中包含三个Java文件。第一个Java文件是`TrieNode.java`，它表示一个前缀树的节点。第二个Java文件是`Main.java`，它包含了项目的主要逻辑。第三个Java文件是`Trie.java`，它实现了一个前缀树的数据结构。这些文件按照层级关系显示在图中，使得文件和文件夹的结构清晰可见。

# 文件列表 File List

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| [Trie.java](Trie.md) | file | 该类实现了 Trie 数据结构，提供插入单词、自动补全、获取所有单词、打印 Trie 结构和拼写建议等功能。插入和自动补全使用前缀查询，拼写建议基于 Levenshtein 距离算法。 |
| [TrieNode.java](TrieNode.md) | file | 这是一个Trie树节点的Java类，包含子节点Map和表示结尾的布尔值。可以存储字符值，并提供判断是否存在特定字符子节点的方法。 |
| [Main.java](Main.md) | file | 这个程序是一个利用前缀树（Trie）实现的字典，能够搜索、补全、删除和获取拼写建议。通过初始化Trie树并调用对应函数实现功能，并通过控制台与用户交互。 |


