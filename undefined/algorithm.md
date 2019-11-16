# Algorithm

```text
import java.util.*;

public class study {
    public static void main(String[] args) {
        int[] arr = new int[]{1,2,3,4};
        System.out.println(Arrays.toString(arr));
        poserSet(arr,0);
        //조합, 순열
        System.out.println("///////////////////////");
        permutation(arr,new boolean[arr.length],0,3,0);

        System.out.println("///////////////////////");
        //sort comparable 이랑 comparator

        List<Node> list = new ArrayList<>();
        list.add(new Node(1,2));
        list.add(new Node(1,3));
        list.add(new Node(2,5));
        list.add(new Node(4,2));
        list.add(new Node(3,2));
        System.out.println("정렬하기전"+list);
        Collections.sort(list);
        System.out.println("기본정렬후"+list);
        Collections.sort(list, new Comparator<Node>() {
            @Override
            public int compare(Node o1, Node o2) {
                return o1.b<o2.b?1:-1;
            }
        });
        System.out.println("특정기준정렬후"+list);

        System.out.println("/////90도회전//////////////////");
        int a[][] = new int[5][5];
        int b[][] = new int[5][5];
        int row,col;
        int idx=1;

        for(row=0;row<5;row++){
            for(col=0;col<5;col++){
                a[row][col]=idx++;
            }
        }
        for(int i=0;i<5;i++){
            System.out.println(Arrays.toString(a[i]));
        }

        for(row=0;row<5;row++){
            for(col=0;col<5;col++){
                b[row][col]= a[col][4-row];
            }
        }
        System.out.println("-90도회전//////////////////");
        for(int i=0;i<5;i++){
            System.out.println(Arrays.toString(b[i]));
        }
        for(row=0;row<5;row++){
            for(col=0;col<5;col++){
                b[row][col]= a[4-col][row];
            }
        }
        System.out.println("90도회전//////////////////");
        for(int i=0;i<5;i++){
            System.out.println(Arrays.toString(b[i]));
        }

    }
    static int N;
    static void poserSet(int[] arr,int idx){
        if(idx==arr.length-1){
            System.out.println(Arrays.toString(arr));
            return;
        }
        for(int i=idx;i<arr.length;i++){
            swap(arr,i,idx);
            poserSet(arr,idx+1);
            swap(arr,i,idx);
        }
    }
    static void swap(int[] arr, int a, int b){
        int tmp = arr[a];
        arr[a]=arr[b];
        arr[b]=tmp;
    }

    static void permutation(int[] arr, boolean[] select,int idx, int r,int count){
        if(idx==arr.length-1){
            if(count==r){
                int[] sel_arr = new int[r];
                int sel_idx=0;
                for(int i=0;i<arr.length;i++){
                    if(select[i]){
                        sel_arr[sel_idx]=arr[i];
                        sel_idx++;
                    }
                }
//                System.out.println(Arrays.toString(sel_arr));
                poserSet(sel_arr,0);
            }
            return;
        }
        select[idx]=true;
        permutation(arr,select,idx+1,r,count+1);
        select[idx]=false;
        permutation(arr,select,idx+1,r,count);
    }

    static class Node implements Comparable<Node>{
        int a;
        int b;

        public Node(int a, int b) {
            this.a = a;
            this.b = b;
        }

        public int getA() {
            return a;
        }

        public void setA(int a) {
            this.a = a;
        }

        public int getB() {
            return b;
        }

        public void setB(int b) {
            this.b = b;
        }

        @Override
        public String toString() {
            return "Node{" + "a=" + a + ", b=" + b + "}\n";
        }

        @Override
        public int compareTo(Node o) {
            if(this.a == o.a){
                return this.b-o.b;
            }
            return this.a-o.a;
        }
    }
}
```



