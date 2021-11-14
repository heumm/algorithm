## [K번째수](https://programmers.co.kr/learn/courses/30/lessons/42748)
***
```java
import java.util.Arrays;

class Solution {
    public int[] solution(int[] array, int[][] commands) {
        int[] answer = new int[commands.length];
        int[] subArr = {};
        int answerIdx = 0;
        int subIdx = 0;
        int i = 0;
        int j = 0;
        int k = 0;

        for(int[] arr : commands) {     //commands : [2,5,3]
            i = arr[0]-1;   //인덱스 뽑아내려고 -1했음
            j = arr[1];
            k = arr[2]-1;
            subArr = new int[j-i];  //5 - 1 = 4
            subIdx = 0;

            for(int n=i; n<j; n++) {
                subArr[subIdx] = array[n];
                subIdx++;
            }

            Arrays.sort(subArr);
            answer[answerIdx] = subArr[k];
            answerIdx++;
        }
        return answer;
    }
}
```