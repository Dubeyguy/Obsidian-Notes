
![](Pasted%20image%2020260904223109.png)

## Array Operations

- Accessing : O(1)
- Inserting : O(1)/ O(n)
- Deletion : O(1) / O(n)
- Traversal : O(n)
- Search : O(n) *linear search* / O(Logn) *binary search*
- Update : O(1)

## Benefits

- Random access time complexity is O(n)
- Cache friendly
- Ease of sorting
- Implements other data structures

## Limitations

- Fixed size. Not good for dynamic problems
- Insertion/Deletion at O(n) time complexity
- Inefficient for frequent modifications

## Use cases

- Implementing other data structures
- Caching or memorization
- Keeping track of visited nodes
- Mathematical computation

## Problems

### Two Sum

![](Pasted%20image%2020260904231028.png)


```go
package main

func twoSum(nums []int, target int) []int {

    // Create a map to store numbers and their indices

    m := make(map[int]int)

    // Iterate through the array

    for i, num := range nums {

        // Calculate the complement of the current number

        complement := target - num

        // Check if the complement is already in the map

        if prevIndex, exists := m[complement]; exists {

            // If found, return the indices of the complement and the current number

            return []int{prevIndex, i}

        }

        // Otherwise, add the current number and its index to the map

        m[num] = i

    }

    return nil

}
```

### Contains Duplicate

![](Pasted%20image%2020260904232521.png)

```go

```