
package org.example;

import java.util.StringTokenizer;

/**
 * <pre>
 *     JadenCase 문자열 만들기
 * </pre>
 *
 * @author 문호환
 * @since 2024-03-08
 */

public class Main {
    public static void main(String[] arg) {
        Solution s = new Solution();

        // TestCase1
        String result1 = "3people unFollowed me";

        // TestCase2
        String result2 = "for the last week";

        System.out.println(s.solution(result1));
    }

    public static class Solution {
        String solution(String result) {
            String answer = "";
            result = result.trim().toLowerCase();

            StringTokenizer stn = new StringTokenizer(result, " ");
            StringBuilder sb = new StringBuilder();

            while (stn.hasMoreTokens()) {
                String token = stn.nextToken();
                String replaceToken = token.replace(token.substring(0, 1), token.substring(0, 1).toUpperCase());
                sb.append(replaceToken + " ");
            }
            answer = sb.toString().trim();
            return answer;
        }
    }

}
