# Floyd



```text
import java.util.Arrays;

public class Floyd {
   static int INF = 9999;
   static int w[][] = { { 0, 4, 2, 5, INF }, { INF, 0, 1, INF, 4 }, { 1, 3, 0, 1, 2 }, { -2, INF, INF, 0, 2 },
         { INF, -3, 3, 1, 0 } };

   public static void main(String[] args) {
      for (int k = 0; k < w.length; k++) {
         for (int i = 0; i < w.length; i++) {
            for (int j = 0; j < w[i].length; j++) {

               w[i][j] = Math.min(w[i][k] + w[k][j], w[i][j]);
            }
         }
      }

      for (int[] row : w) {
         System.out.println(Arrays.toString(row));
      }
   }
}
```

