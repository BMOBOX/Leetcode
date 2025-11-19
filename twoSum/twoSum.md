## Basics

# Hashmap

- unordered_map
declaration: ```unordered_map<int, int> u_name;``` //(index : number)

a. functions:

1. u_name.find(index) returns first occurence
2. u_name.count(index) return total occurences

___


## Code

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) { 
        unordered_map<int, int> h;
        for (int i = 0; i < nums.size(); i++){
            auto it = h.find(nums[i]);
            if(it != h.end()){    
                return vector<int>{it->second, i};
            }
            h[target - nums[i]] = i;
        }
        return vector<int>{};
    }
};
```
