# combination_sum

class Solution(object):
    def combinationSum(self, candidates, target):
        dp = [[] for i in range(target+1)]
        
        for c in candidates:
            for i in range(target+1):
                if i<c: continue
                if i==c:
                    dp[i].append([c])
                else:
                    for blist in dp[i-c]:
                        dp[i].append(blist+[c])
        return dp[target]
