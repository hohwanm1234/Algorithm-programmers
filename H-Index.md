```java


package org.example;

import java.util.Arrays;

/**
 * <pre>
 *     H-Index
 * </pre>
 *
 * @author 문호환
 * @since 2024-03-20
 */

public class Main {
    public static void main(String[] arg) {
        Solution s = new Solution();

        // TestCase1
        int[] A = {3,0,6,1,5};

        System.out.println(s.solution(A));
    }


    public static class Solution {
        int solution(int[] citations) {
            int answer = 0;

            Arrays.sort(citations); // [0, 1, 3, 5, 6]

            for(int i=0; i<citations.length; i++) {
                int h = citations.length-i; // 인용된 논문

                if(citations[i] >= h) {     // 배열의 숫자가 인용된 논문(h) 보다 크거나 같아질 경우
                    answer = h;
                    break;
                }
            }

            return answer;
        }
    }
}


```
