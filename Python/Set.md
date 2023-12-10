## Characteristics
* Does not store duplicate values
* Unordered
	* Cannot retrieve value by index

## Usages
### Algorithm-Wise
* when you want to check whether some data has already been used*

## Init
```python
# init
data = set([1,1,2,3,4,4,5]) # {1,2,3,4,5}
data2 = {1,1,2,3,4,4,5} # {1,2,3,4,5}
```
## Operations
```python
# operations
a = set([1,2,3,4,5])
b = set([3,4,5,6,7])
# union
a | b # {1,2,3,4,5,6,7}
# intersection
a & b # {3,4,5}
# diff
a - b # {1,2}
```
## Functions
```python
data = set([1,2,3])
data.add(4) #{1,2,3,4}
data.update([3,4,5,6]) #{1,2,3,4,5,6}
data.remove(3) #{1,2,4,5,6}
```