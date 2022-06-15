# 198.-House-Robber
leetcode question(https://leetcode.com/problems/house-robber/)
![image](https://user-images.githubusercontent.com/102652030/173782535-cd68c335-dd4b-4a78-996e-a193724a5182.png)


class Solution {
public:
    int rob(vector<int>& nums) {
        int n=nums.size();
        vector<int> dp(n+1,-1);
        dp[1]=nums[0];
        if(n>1)
        dp[2]=max(nums[0],nums[1]);
        for(int i=3;i<=n;i++){
            int op1=dp[i-1];
            int op2=dp[i-2]+nums[i-1];
            dp[i]=max(op1,op2);
        }
        return dp[n];
    }
};
