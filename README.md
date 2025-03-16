# CODING

TWO SUM
BRUTE FORCE
class Solution {
    public int[] twoSum(int[] nums, int target) {
        int n=nums.length;
        int arr[]=new int[2];
        for(int i=0;i<n;i++){
            for(int j=i+1;j<n;j++){
                if(nums[i]+nums[j]==target){
                arr[1]=j;
                arr[0]=i;
                }
            }
        }
        return arr;
    }
}

BETTER APPROACH USING HASHMAP
class Solution {
    public int[] twoSum(int[] nums, int target) {
        HashMap<Integer,Integer> map=new HashMap<>();
        for(int i=0;i<nums.length;i++){
            int numneeded=target-nums[i];

            if(map.containsKey(numneeded)){
                return new int[]{map.get(numneeded),i};
            }

            map.put(nums[i],i);
        }
        return new int[]{0,0};
    }
}
