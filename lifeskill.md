## Data types of JavaScript
There are two Data types
    1. Primitive date type
    2. Non-Primitive date type
## Primitive data types
Again There are five types of primitive data types in JavaScript that is 

1. String
String represents sequence of characters and it should be enclosed with single quote and double quote.
Example: 
        const name = 'Vinayaka';
        const name = "Vinayaka raju";

2. Number
Number represents numeric values
Example:
         const number1 = 3/0;
         console.log(number1);
         
3. Boolean
Boolean represents one of two values either true or false
Example:
          const dataChecked = true;
          const valueCounted = false;
       
4. Undefined
Undefined represents undefined value
Example:
        data is of undefined type
        let data;

5. Null
Null is a special value that represents an empty or unkmown value.
Example:
         const a = null;
         typeof(a); // returns "object"

## Non-Primitive date types ##
1. Object 
Object is an entity having state and behaviour like properties and method.
Example:
         const person = {name:'vinayaka'age:20};

2. Array
An array is an object that can store multiple values at once or represents regular expression
Example: 
        const cars = ["Maruthi", "BMW", "MG"];

3. RegExp
A regular expression is a sequence of characters that forms a search pattern.
Example:
        let text = "visit Mountblue";
        let n = 
        text.search(/Mountblue/i);

### Data structures in JavaScript ###
There are 8 common data structures in JavaScript.
1. stack
A stack data structure holds a list of elements and work on the principle of LIFO(last in First out)and two main operations that occur at the top of the stack, which are push and pop.

* Sample code:

function Stack() {
this.count = 0;
  this.storage = {};
  this.push = function (value) {
    this.storage[this.count] = value;
    this.count++;
  }
  this.pop = function () {
if (this.count === 0) {
   return undefined;
}
    this.count--;
var result = this.storage[this.count];
delete this.storage[this.count];
return result;
  }
  this.peek = function () {
return this.storage[this.count - 1];
  } 
  this.size = function () {
return this.count;
  }
}
# References 
If you want more examples go through this link
* https://builtin.com/software-engineering-perspectives/javascript-data-structures

2. Queue
Queue is a linear data structure tht follows the FIFO(First in First Out)principle.it contains two pointers 
      1 front pointer
      2 rear pointer
The front pointer contains the address of the starting element of the queue.
The rear pointer contains the address of the last element of the queue.

* Sample code:

  function Queue() {
  var collection = [];
  this.print = function () {
    console.log(collection);
  }
  this.enqueue = function (element) {
    collection.push(element);
  }
  this.dequeue = function () {
return collection.shift();
  }
  this.front = function () {
return collection[0];
  } 
  this.isEmpty = function () {
return collection.length === 0;
  }
  this.size = function () {
return collection.length;
  }
}
# References 
If you want more examples go through this link
* https://builtin.com/software-engineering-perspectives/javascript-data-structures

3. Linked List
A Linked List is a chained data structure.Each node consists of two pieces of information.The data of node and the pointer to the next node.Linked list and conventional array are both linear data structures with serialized storage.

* sample code

function Node(element) { 
// Data in the node
    this.element = element; 
// Pointer to the next node
    this.next = null;
}
    function LinkedList() { 
        var length = 0; 
        var head = null; 
        this.size = function () {
            return length; 
        } 
        this.head = function () {
            return head; 
        } 
        this.add = function (element) {   
            var node = new Node(element);
            if (head == null) { 
                head = node;  
         } else { 
                var currentNode = head; 
                while (currentNode.next) {        
                 currentNode = currentNode.next; 
                } 
                currentNode.next = node;
            }
            length++; 
        } 
        this.remove = function (element) {   
            var currentNode = head;
            var previousNode;
            if (currentNode.element === element) { 
                head = currentNode.next;
            } else { 
                while (currentNode.element !== element) {   
                 previousNode = currentNode;   
                 currentNode = currentNode.next;
          } 
                previousNode.next = currentNode.next;   
            }   
            length--; 
        } 
        this.isEmpty = function () {
            return length === 0; 
        } 
        this.indexOf = function (element) {   
            var currentNode = head;
            var index = -1;    
            while (currentNode) { 
                index++; 
                if (currentNode.element === element) {   
                 return index; 
                } 
                currentNode = currentNode.next;
            }   
            return -1; 
        } 
        this.elementAt = function (index) {   
            var currentNode = head;
            var count = 0;
            while (count < index) { 
                count++; 
                currentNode = currentNode.next;   
            }
            return currentNode.element; 
        } 
        this.addAt = function (index, element) {
            var node = new Node(element);
            var currentNode = head;
            var previousNode;
            var currentIndex = 0;
            if (index > length) {
                return false;
            }
            if (index === 0) { 
                node.next = currentNode; 
                head = node;
            } else { 
                while (currentIndex < index) {       
                 currentIndex++;   
                 previousNode = currentNode;   
                 currentNode = currentNode.next; 
                } 
                node.next = currentNode; 
                previousNode.next = node;
            }
            length++; 
        } 
        this.removeAt = function (index) {   
            var currentNode = head;
            var previousNode;
            var currentIndex = 0;
            if (index < 0 || index >= length) { 
                return null;    
            }
            if (index === 0) { 
                head = currentIndex.next;
            } else { 
                while (currentIndex < index) {       
                 currentIndex++;   
                 previousNode = currentNode;   
                 currentNode = currentNode.next; 
                } 
                previousNode.next = currentNodenext;   
            }
            length--;
            return currentNode.element; 
     }
}
# Reference 
If you want more examples go through this link
* https://www.simplilearn.com/common-data-structures-in-javascript-article

4. Set
Set is a collection of well defined and distinct objects, a set does not allow repeating elements and is not indexed.

* Sample code:
 function MySet() {  
    var collection = [];  
    this.has = function (element) {    
        return (collection.indexOf(element) !== -1);  
    }  
    this.values = function () {    
        return collection;  
    }  
    this.size = function () {    
        return collection.length;  
    }  
    this.add = function (element) {    
        if (!this.has(element)) {      
            collection.push(element);      
            return true;    
        }    
        return false;  
    }  
    this.remove = function (element) {    
        if (this.has(element)) {      
            index = collection.indexOf(element);      
            collection.splice(index, 1);      
            return true;    
        }    
        return false;  
    }  
    this.union = function (otherSet) {    
        var unionSet = new MySet();    
        var firstSet = this.values();    
        var secondSet = otherSet.values();    
        firstSet.forEach(function (e) {      
            unionSet.add(e);    
        });    
        secondSet.forEach(function (e) {      
            unionSet.add(e);    
        });    
        return unionSet;  }  
        this.intersection = function (otherSet) {    
            var intersectionSet = new MySet();    
            var firstSet = this.values();    
            firstSet.forEach(function (e) {      
                if (otherSet.has(e)) {        
                    intersectionSet.add(e);      
                }    
            });    
            return intersectionSet;  
        }  
        this.difference = function (otherSet) {    
            var differenceSet = new MySet();    
            var firstSet = this.values();    
            firstSet.forEach(function (e) {      
                if (!otherSet.has(e)) {        
                    differenceSet.add(e);      
                }    
            });    
            return differenceSet;  
        }  
        this.subset = function (otherSet) {    
            var firstSet = this.values();    
            return firstSet.every(function (value) {      
                return otherSet.has(value);    
            });  
        }
    }
# Reference
If you want more examples go through this link
* https://builtin.com/software-engineering-perspectives/javascript-data-structures

5. Hash Table
A hash table is an implementation of an associative array, a list of key value pairs that allow you to retrieve a value via a key.A hash represents the value of the corresponding key.

* sample code:

var Mountblue = new Object();
// or
// var Mountblue = {};
Mountblue['key2'] = 'value2';
Mountblue['key3'] = 'value3';

for (var key in Mountblue) {
  // use hasOwnProperty() to filter out properties from Object.prototype
  if (Mountblue.hasOwnProperty(key)) {
    console.log('key is: ' + key + ', value is: ' + Mountblue[key]);
  }
}
6. Tree
Tree is a non linear, multi layer data structure which proves to be highly efficient during insert and search operations. Trees are a data structures that link nodes in a parent/child relationship, in the sense that there are nodes that depend on or come off other nodes.

* Sample code:

class Node {
  constructor(data, left = null, right = null) {
    this.data = data;
    this.left = left;
    this.right = right;
  }
}

class BST {
  constructor() {
    this.root = null;
  }

  add(data) {
    const node = this.root;
    if (node === null) {
      this.root = new Node(data);
      return;
    } else {
      const searchTree = function (node) {
        if (data < node.data) {
          if (node.left === null) {
            node.left = new Node(data);
            return;
          } else if (node.left !== null) {
            return searchTree(node.left);
          }
        } else if (data > node.data) {
          if (node.right === null) {
            node.right = new Node(data);
            return;
          } else if (node.right !== null) {
            return searchTree(node.right);
          }
        } else {
          return null;
        }
      };
      return searchTree(node);
    }
  }

  findMin() {
    let current = this.root;
    while (current.left !== null) {
      current = current.left;
    }
    return current.data;
  }

  findMax() {
    let current = this.root;
    while (current.right !== null) {
      current = current.right;
    }
    return current.data;
  }

  find(data) {
    let current = this.root;
    while (current.data !== data) {
      if (data < current.data) {
        current = current.left
      } else {
        current = current.right;
      }
      if (current === null) {
        return null;
      }
    }
    return current;
  }

  isPresent(data) {
    let current = this.root;
    while (current) {
      if (data === current.data) {
        return true;
      }
      if (data < current.data) {
        current = current.left;
      } else {
        current = current.right;
      }
    }
    return false;
  }

  remove(data) {
    const removeNode = function (node, data) {
      if (node == null) {
        return null;
      }
      if (data == node.data) {
        // no child node
        if (node.left == null && node.right == null) {
          return null;
        }
        // no left node
        if (node.left == null) {
          return node.right;
        }
        // no right node
        if (node.right == null) {
          return node.left;
        }
        // has 2 child nodes
        var tempNode = node.right;
        while (tempNode.left !== null) {
          tempNode = tempNode.left;
        }
        node.data = tempNode.data;
        node.right = removeNode(node.right, tempNode.data);
        return node;
      } else if (data < node.data) {
        node.left = removeNode(node.left, data);
        return node;
      } else {
        node.right = removeNode(node.right, data);
        return node;
      }
    }
    this.root = removeNode(this.root, data);
  }
}
# Reference
If you want more examples go through this link
* https://www.codecademy.com/resources/docs/javascript/hashtables
7. Trie
Trie stores the data step by step, each node in the tree represents a step. it is especially useful for the auto-complete function.

* sample code:

function Node() {  
    this.keys = new Map();  
    this.end = false;  
    this.setEnd = function () {    
        this.end = true;  
    };  
    this.isEnd = function () {    
        return this.end;  
    }
}

function Trie() {  
        this.root = new Node();  
        this.add = function (input, node = this.root) {    
            if (input.length === 0) {     
                node.setEnd();      
                return;    
            } else if (!node.keys.has(input[0])) {      
                node.keys.set(input[0], new Node());      
                return this.add(input.substr(1), node.keys.get(input[0]));    
            } else {      
                return this.add(input.substr(1), node.keys.get(input[0]));    
            }  
        }  
        this.isWord = function (word) {    
            let node = this.root;    
            while (word.length > 1) {      
                if (!node.keys.has(word[0])) {        
                    return false;      
                } else {        
                    node = node.keys.get(word[0]);       
                    word = word.substr(1);      
                }    
            }    
            return (node.keys.has(word) && node.keys.get(word).isEnd()) ? true : false;  
        }  
            this.print = function () {    
                let words = new Array();    
                let search = function (node = this.root, string) {      
                    if (node.keys.size != 0) {        
                        for (let letter of node.keys.keys()) {          
                            search(node.keys.get(letter), string.concat(letter));        
                        }        
                        if (node.isEnd()) {          
                            words.push(string);        
                        }      
                    } else {        
                        string.length > 0 ? words.push(string) : undefined;        
                        return;      
                    }    
                };    
                search(this.root, new String());    
                return words.length > 0 ? words : null;  
    }
}
# Reference
If you want more examples go through this link
* https://www.codecademy.com/resources/docs/javascript/hashtables
8. Graph
A graph is a data structure where a node can have zero or more adjacent elements. The connection between two nodes is called edge. We use graphs in our daily lives without even realizing it. Graphs help calculate the best route in navigation apps or recommend friends with whom we might like to connect.

* Sample code

function bfs(graph, root) {
  var nodesLen = {};
  for (var i = 0; i < graph.length; i++) {
    nodesLen[i] = Infinity;
  }
  nodesLen[root] = 0;
  var queue = [root];
  var current;
  while (queue.length != 0) {
    current = queue.shift();

    var curConnected = graph[current];
    var neighborIdx = [];
    var idx = curConnected.indexOf(1);
    while (idx != -1) {
      neighborIdx.push(idx);
      idx = curConnected.indexOf(1, idx + 1);
    }
    for (var j = 0; j < neighborIdx.length; j++) {
      if (nodesLen[neighborIdx[j]] == Infinity) {
        nodesLen[neighborIdx[j]] = nodesLen[current] + 1;
        queue.push(neighborIdx[j]);
      }
    }
  }
  return nodesLen;
}
# References 
If you want more examples go through this link
* https://www.codecademy.com/resources/docs/javascript/hashtables
