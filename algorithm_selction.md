theme: jekyll-theme-cayman

# 선택정렬(selection sort)

제자리 정렬 알고리즘의 하나

## 방법
(1) 주어진 리스트 중에서 최소값을 찾는다.
(2) 그 값을 맨 앞에 위치한 값과 교체한다.
(3) 맨 처음 위치를 뺀 나머지 리스트를 같은 방법으로 교체한다.


```markdown
![Image](https://dduddupark.github.io/algorithm/selection.PNG)
```

## 코드

public class SelectionSort {
    
	public void selectionSort(int[] list, int size) {
    
        int least, temp=0;  //최소값 위치, 임시 저장 변수
    
        for (int i=0; i<(size-1); i++) {  //i는 0번부터 3번까지 비교한다.
            
            least = i;
            
            for(int j=(i+1); j<size; j++) { //j는 i+1(i 다음)부터 4번(마지막)까지 비교한다.
                if (list[j] < list[least]) {
                    least = j;
                }
            }
            
            if(least != i) {  //i와 같으면 변경 할 위치가 없는 것이다.
            
               //swap
          
               temp = list[i];
            	 list[i] = list[least];
            	 list[least] = temp;
            }
        } 
    
	}
} 

public class Main
{
	public static void main(String[] args) {
  
		int[] list = {10, 8, 9, 1, 2};
		
		System.out.println("before = " + list[0] + " , " + list[1] + " , " +  list[2] + " , " +  list[3]+ " , " +  list[4]);
	
		SelectionSort selectionSort = new SelectionSort();
		
		selectionSort.selectionSort(list, 5);
		
		System.out.println("after = " + list[0] + " , " + list[1] + " , " +  list[2] + " , " +  list[3]+ " , " +  list[4]);
	}
}


## 결과

before = 10 , 8 , 9 , 1 , 2                                                                                                                    
after = 1 , 2 , 8 , 9 , 10

## 출처

https://ko.wikipedia.org/wiki/%EC%84%A0%ED%83%9D_%EC%A0%95%EB%A0%AC
