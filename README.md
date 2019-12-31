# learn-LinkedHashMap

* **Hash table and linked list implementation of the Map interface, with predictable iteration order. This implementation differs from HashMap in that it maintains a doubly-linked list running through all of its entries. This linked list defines the iteration ordering, which is normally the order in which keys were inserted into the map (insertion-order). Note that insertion order is not affected if a key is re-inserted into the map. (A key k is reinserted into a map m if m.put(k, v) is invoked when m.containsKey(k) would return true immediately prior to the invocation.)**

* 与HashMap不同， LinkedHashMap提供了“顺序可预测”的Map实现： 与元素插入的顺序相同，并且重复插入同一元素（同一key值）顺序并不受影响

* **This implementation spares its clients from the unspecified, generally chaotic ordering provided by HashMap (and Hashtable), without incurring the increased cost associated with TreeMap. It can be used to produce a copy of a map that has the same order as the original, regardless of the original map's implementation**

* 该实现提供了HashMap或HashTable所不具备的保证元素顺序的能力， 同时又不会像TreeMap那样为了此种能力而增加了额外的成本（get方法大于常数阶）。它还可用于从一个即有Map的实现生成一个保持顺序的LinkedHashMap的副本。

* **A special constructor is provided to create a linked hash map whose order of iteration is the order in which its entries were last accessed, from least-recently accessed to most-recently (access-order). This kind of map is well-suited to building LRU caches.**

* 构造函数中的中的 accessOrder 参数可提供使LinkedHashMap根据访问顺序排序的能力， 非常适合实现LRU
