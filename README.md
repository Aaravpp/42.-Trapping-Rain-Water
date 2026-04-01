INTUTION: 

The amount of water trapped at any index depends on the height of the tallest bar on the left and right.
Water level at index i = min(maxLeft[i], maxRight[i])
Trapped water = water level - height[i]

So, for each index:
Find the maximum height to its left
Find the maximum height to its right
The smaller of the two limits the water

APPROACH:

1. Create two arrays:
    maxL[i]: maximum height from index 0 → i
    maxR[i]: maximum height from index n-1 → i
2. Fill maxL:
    maxL[i] = max(maxL[i-1], arr[i])
3. Fill maxR:
    Traverse from right
    maxR[i] = max(maxR[i+1], arr[i])
4. For each index:
    Water trapped = min(maxL[i], maxR[i]) - arr[i]
    Add only if positive

Complexity:
    Time complexity: O(n)
    Space complexity: O(n)
