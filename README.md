# Learning usage of STL in ACM
> Notes for reading posts on [topcoder1](https://www.topcoder.com/community/data-science/data-science-tutorials/power-up-c-with-the-standard-template-library-part-1/#vector) and [post2](https://www.topcoder.com/community/data-science/data-science-tutorials/power-up-c-with-the-standard-template-library-part-2/)

## Summary
There are there things in STL

1. Container
    1. vector
    2. string
    3. map
    4. list
    5. stack
2. Iterator
3. Algorithm
    1. find
    2. sort

### Somethings before we start
```cpp
#include <iostream>
#include <vector>
#include <string>
#include <map>
#include <stack>
#include <list>
#include <algorithm>

using namespace std;
```

## Container
### vector
common usage of vecotr
```cpp
// create a vector variable
vector<int> v;
vector<int> v(10);
vector<int> v(10, 1); // create a vector with 10 elements of integer;
vector<int> v2(v1); // copy constuctor
vector<int> v2 = v1; // the same with above
// vector<int> v[10]; // define an array of vector<int>, which is not what we want

// member function of vector
cout << v.size(); // get the size of vector, return a unsiged int, shouldn't be using to compare with 0
if (v.empty()) {
    cout << "v is empty\n";
}
v.resize(20); // resize the vector
v.clear(); // clear all the elements

// add elements to a vector
v.push_back(1);
v.insert(v.begin(), 2); //insert a value at given position, the position should be an iterator
v.erase(v.begin()); // pass an interator as parameter

// access elements of a vecotor
cout << v[0];
cout << *(v.begin()); // using iterator

// two dimensions of vector with n x m elements
vector<vector<int> > v(n, vector<int>(m));
```

### string
```cpp
string s = "hello";
string s1 = s.substr(0, 3); // "hel"
string s2 = s.substr(1); // "ello"
```

### set
```cpp
set<int> s;
s.insert(1);
s.erase((0);
cout << s.size();

// searching in set && map, we should not use the find function offered by the <algorithm> which is O(n).
// instead, we can using the member function of set && map which is O(lg N)
if (s.find(1) != s.end()) {
    cout << "found\n";
}
```

### map
```cpp
map<string, int> M;
M["hello"] = 12;
M["world"] = 42;
cout << M["hello"];

// map.find() will not change the map, but operator[] on map will create a new key if it doesn't exist
// internal storage of map && set is red black tree, transeval of it is in accending order
if(M.find("hello") != M.end()) {
    M.erase(M.find("hello");
}
```

## Iterator
before we come to interator, let's talk about pairs
### pairs
The most useful feature of pair is that it can be compared with itself, from the first member to the second member.

```cpp
// define a pair
pair<int, int> p;

// access member in a pair
cout << p.first;
cout << p.second;
```

## Algorithm
### max && min
max(a, b)
min(a, b)
max_element
min_element

```cpp
int max_number = *max_element(v);
int min_number = *min_element(v);
```

### find
```cpp
if (find(v.begin(), v.end(), 49) != v.end()) {
    cout << "found\n";
}
```

### count
```
count(v.begin(), v.edn(), 49); //return the occurance of specified number
```
### sort
> need random accessed iterator

```cpp
sort(v.begin(), v.end());
sort(v.rbegin(), v.rend();
```

swap

### reserve
```cpp
reserve(v.begin(), b.end())
```

### copy
```cpp
copy(v.begin(), b.end(), v2.begin())
```

### accumulate


## Todo
1. look for a big integer template
