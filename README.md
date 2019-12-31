# learn-LinkedHashMap

* **Hash table and linked list implementation of the Map interface, with predictable iteration order. This implementation differs from HashMap in that it maintains a doubly-linked list running through all of its entries. This linked list defines the iteration ordering, which is normally the order in which keys were inserted into the map (insertion-order). Note that insertion order is not affected if a key is re-inserted into the map. (A key k is reinserted into a map m if m.put(k, v) is invoked when m.containsKey(k) would return true immediately prior to the invocation.)**

* 与HashMap不同， LinkedHashMap提供了“顺序可预测”的Map实现： 与元素插入的顺序相同，并且重复插入同一元素（同一key值）顺序并不受影响

* **This implementation spares its clients from the unspecified, generally chaotic ordering provided by HashMap (and Hashtable), without incurring the increased cost associated with TreeMap. It can be used to produce a copy of a map that has the same order as the original, regardless of the original map's implementation**

* 该实现提供了HashMap或HashTable所不具备的保证元素顺序的能力， 同时又不会像TreeMap那样为了此种能力而增加了额外的成本（get方法大于常数阶）。它还可用于从一个即有Map的实现生成一个保持顺序的LinkedHashMap的副本。

* **A special constructor is provided to create a linked hash map whose order of iteration is the order in which its entries were last accessed, from least-recently accessed to most-recently (access-order). This kind of map is well-suited to building LRU caches.**

* 构造函数中的中的 accessOrder 参数可提供使LinkedHashMap根据访问顺序排序的能力， 非常适合实现LRU

* **Like HashMap, it provides constant-time performance for the basic operations (add, contains and remove), assuming the hash function disperses elements properly among the buckets. Performance is likely to be just slightly below that of HashMap, due to the added expense of maintaining the linked list, with one exception: Iteration over the collection-views of a LinkedHashMap requires time proportional to the size of the map, regardless of its capacity. Iteration over a HashMap is likely to be more expensive, requiring time proportional to its capacity.**

* LinkedHashMap的基本操作（add.contains,remove)提供常数阶的性能（前提是元素正确分布在桶数组上--与HasmMap类似）。另外，由于维护链表的额外开销，LinkedHashMap的性能可能会略低于HashMap，但在迭代(Iterator）的情况下则例外， 因LinkedHashMap的迭代性能与其中的元素个数成正比，而与其桶数据的容量无关。HashMap的迭代器则是与其桶数据的容量成正比的。
