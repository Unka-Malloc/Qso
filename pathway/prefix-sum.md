# Prefix Sum

#### [560. 和为K的子数组](https://leetcode.cn/problems/subarray-sum-equals-k/description/)

{% tabs %}
{% tab title="C++" %}
```cpp
class Solution {
public:
    int subarraySum(vector<int>& nums, int k) {
      int ans = 0;
      
      unordered_map<int, int> hashmap;
      hashmap[0] = 1;

      int presum = 0;
      for (auto x: nums) {
        presum += x;

        if (hashmap.count(presum - k)) {
          ans += hashmap[presum-k];
        }

        hashmap[presum] += 1;
      }

      return ans;
    }
};
```
{% endtab %}

{% tab title="Python" %}
```python
class Solution:
    def subarraySum(self, nums: List[int], k: int) -> int:
      ans = 0
      
      memory = {0: 1}
      
      prefix_sum = 0
      for i in range(len(nums)):
        prefix_sum += nums[i]

        if (prefix_sum - k) in memory:
          ans += memory[prefix_sum - k]

        if prefix_sum in memory:
          memory[prefix_sum] += 1
        else:
          memory[prefix_sum] = 1

      return ans
```
{% endtab %}
{% endtabs %}
