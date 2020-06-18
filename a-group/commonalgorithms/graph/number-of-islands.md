---
description: Typical Breadth first search
---

# Number of Islands

Given a 2d grid map of `'1'`s \(land\) and `'0'`s \(water\), count the number of islands. An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.

**Example 1:**

```text
Input:
11110
11010
11000
00000

Output: 1
```

**Example 2:**

```text
Input:
11000
11000
00100
00011

Output: 3
```

```java
class Solution {
    public int numIslands(char[][] grid) {
        int res = 0;
        for (int row = 0; row < grid.length; row++) {
            for (int col = 0; col < grid[0].length; col++) {
                if (grid[row][col] == '0' || grid[row][col] == '*') {
                    continue;
                }
                res++;
                Queue<String> queue = new LinkedList<String>();
                queue.offer(row + "," + col);
                grid[row][col] = '*';
                while(!queue.isEmpty()) {
                    String curCors = queue.poll();
                    String[] cors = curCors.split(",");
                    int rowNum = Integer.valueOf(cors[0]);
                    int colNum = Integer.valueOf(cors[1]);                    
                    
                    if(colNum + 1 < grid[0].length && grid[rowNum][colNum + 1] == '1') {
                        queue.offer(rowNum + "," + String.valueOf(colNum + 1));
                        grid[rowNum][colNum + 1] = '*';
                    }
                    if(rowNum + 1 < grid.length && grid[rowNum + 1][colNum] == '1') {
                        queue.offer(String.valueOf(rowNum + 1) + "," + colNum);
                        grid[rowNum + 1][colNum] = '*';
                    }
                    if(colNum - 1 >= 0 && grid[rowNum][colNum - 1] == '1') {
                        queue.offer(rowNum + "," + String.valueOf(colNum - 1));
                        grid[rowNum][colNum - 1] = '*';
                    }
                    if(rowNum - 1 >= 0 && grid[rowNum - 1][colNum] == '1') {
                        queue.offer(String.valueOf(rowNum - 1) + "," + colNum);
                        grid[rowNum - 1][colNum] = '*';
                    }
                }
            }
        }
        return res;
    }
}
```

