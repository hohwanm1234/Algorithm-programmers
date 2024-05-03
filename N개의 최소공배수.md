```java

package org.example;


/**
 * <pre>
 *     N개의 최소공배수
 * </pre>
 *
 * @author 문호환
 * @since 2024-05-03
 */

public class Main {
    public static void main(String[] arg) {
        Solution sol = new Solution();

        // TestCase1
        int[] arr1 = {2,6,8,14};
        System.out.println(sol.solution(arr1));

        sol.resetAnswer();

        // TestCase2
        int[] arr2 = {1,2,3};
        System.out.println(sol.solution(arr2));
    }

    // 유클리드 호제법 - 최대 공약수를 구하는 알고리즘
    // a,b가 주어졌을때, a%b = r(나머지)
    // b%r = s(나머지) 해당 나머지 구하는 방법을 반복 -> 나머지가 0일때(x%y == 0) y가 최대 공약수
    // 최소 공배수 = a * b / 최대공약수
    public static class Solution {
        int answer = 0;

        public void resetAnswer() {
            answer = 0;
        }

        int solution(int[] arr) {
            answer = arr[0];

            for(int i=1; i<arr.length; i++) {
                answer = lcm(answer, arr[i]);
            }

            return answer;
        }

        /**
         * <pre>
         *  최대 공약수 구하기 (greatest common divisor)
         * </pre>
         */
        public static int gcd (int a, int b) {
            if(a % b == 0) {
                return b;
            }
            return gcd(b, a % b);
        }

        /**
         * <pre>
         *  최소 공배수 구하기 (least common multiple)
         * </pre>
         */

        public static int lcm (int a, int b) {
            return a * b / gcd(a, b);
        }
    }
}


```
