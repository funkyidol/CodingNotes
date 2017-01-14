# Java Notes

### Set Interface
The basic idea of Set is the mathematical definition of set where it doesn't allow duplication

**Type of sets**
1. HashSet
 * Stores elements in `HashTable`
 * Best performance
 * No order preservation
2.  TreeSet
 * Stores elements in Red Black Trees
 * Order by values
 * Slower than HashSet
3. LinkedHashSet
 * HashTable with LinkList
 * Order by insertion
 * Slightly slower than HashSet

** Basic Bulk Operations **
1. `s1.containAll(s2)` - returns true if s2 is subset of s1
2. `s1.addAll(s2)` - makes s1 a union of s1 & s2
3. `s1.retainAll(s2)` - makes s1 an intersection of s1 & s2
4. `s1.removeAll(s2)` - makes s1 an assymetric difference of s1 & s2. i.e. contains elements of s1 and removes all elements present in s2

### List Interface

* Sort method in List interface uses Merge Sort

### Map Interface
* Cannot contain duplicate keys
* One key can map to at most one value

----

#### HashSet vs HashMap vs HashTable
HashSet
* Does not allow duplicate values
* Internally its just HashMap where all elements are stored as keys which ensure zero duplication

HashMap
* Key Value pair
* Map interface is not part of the collections framework
* Allows both null key and values
* Not synchronized

HashTable
* Key Value pair
* Does not allow null
* Implements Map interface
* It is synchronized
* Does not allow null key and value

----

#### Static Keyword
* **Variable:** Gets the memory in class area at time of class loading
* **Method:**
 * Belongs to a class rather than an object.
 * Can access static data members
 * Cannot access non-static variables or methods
 * `this` & `super` cannot be used in this methods
* **Block:** Executed before main
* **Nested Class**

#### Final Keyword
* **Variable:** Value cannot be modified. Blank variables have to be initialized in constructor.
* **Method:** Cannot be overridden
* **Class:** Cannot be extended
