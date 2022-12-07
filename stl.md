# STL notes for future ref

--------------------------------------------------------------------------------

### index






--------------------------------------------------------------------------------


### vector

```cpp

vector<int> v;
vector<int> v = {a,c,b};



v.push_back(element);

vector<int> :: iterator i = v.begin();
vector<int> :: iterator j = v.end();


//-------------------------------------------------------------------------------- 

// function

v.size();
v.at(index); // range-check
v[index] // no range check

// recommended traverse with an iterator, its faster and works on any container





```

### deque

- can grow both and front and end

```cpp

deque<int> deq = {4, 6, 7};
deq.push_front(5);
deq.push_back(9);

// similar interface as vector

cout << deq[1] << endl;

```

### list

```cpp

list<int> ls = {4, 99, 2};

ls.push_back(6);
ls.push_front(8);

// {8,4,99,2,6}

ls.insert(iterator, element_to_insert);

// if insert 0 when iter pointing to 4,
// {8,0,4,99,2,6}}

ls.find(start_iter, end_iter, number);
ls.erase(iter_at_that_place);

list<int> ll = {0};

// most powerful function of list

ll.splice(itr_pos, from_list_itr, itr_start, itr_end); // O(1) time complexity


```


### container


##### sequence-container

1. array
2. linked list

STL gives 
    - vector
    - deque
    - list
    - forward list
    - array

##### associative-container
(binary tree)

- set multiset
- map multimap

##### unordered-container
(hash table)

- unordered set/multiset
- unordered map/multimap


##### stl-headers
 
#include <  >

    - vector
    - deque
    - list
    - set
    - map
    - iterator
    - algorithm
    - numeric
    - functional
    - unordered_set
    - unordered_map

### common-member-function

```cpp
    cont.empty();
    cont.size();
    vector<int> v(v2); // copy constructor v2 copy

    cont.clear();
    cont1.swap(cont2); // cont1 empty cont2 has its items




















































