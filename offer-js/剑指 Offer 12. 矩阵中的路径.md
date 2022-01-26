```py
class Solution:
    def exist(self, board: List[List[str]], word: str) -> bool:
        row, col = len(board), len(board[0])
        visited = set()
        res = False
        for i in range(row):
            for j in range(col):
                res = self.dfs(board, word, i, j, 0, visited)
                if res:
                    return True
        return res
    
    def dfs(self, board, word, x, y, k, visited):
        if not 0 <= x < len(board) or not 0 <= y < len(board[0]) or (x, y) in visited or board[x][y] != word[k]:
            return False
        if k == len(word) - 1:
            return True
        visited.add((x, y))

        res = self.dfs(board, word, x + 1, y, k + 1, visited) or self.dfs(board, word, x - 1, y, k + 1, visited) or self.dfs(board, word, x, y + 1, k + 1, visited) or self.dfs(board, word, x, y - 1, k + 1, visited)
        
        visited.remove((x, y))
        return res

        
```        
