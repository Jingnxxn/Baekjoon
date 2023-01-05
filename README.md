<img src="https://capsule-render.vercel.app/api?type=waving&color=auto&height=200&section=header&text=Baekjoon&fontSize=90" /> 

##5597
----------------------

<문제>
X대학 M교수님은 프로그래밍 수업을 맡고 있다. 교실엔 학생이 30명이 있는데, 학생 명부엔 각 학생별로 1번부터 30번까지 출석번호가 붙어 있다.
교수님이 내준 특별과제를 28명이 제출했는데, 그 중에서 제출 안 한 학생 2명의 출석번호를 구하는 프로그램을 작성하시오.
<입력>
입력은 총 28줄로 각 제출자(학생)의 출석번호 n(1 ≤ n ≤ 30)가 한 줄에 하나씩 주어진다. 출석번호에 중복은 없다.
<출력>
출력은 2줄이다. 1번째 줄엔 제출하지 않은 학생의 출석번호 중 가장 작은 것을 출력하고, 2번째 줄에선 그 다음 출석번호를 출력한다.

-------------------------------
```ruby
#include<stdio.h>
int main(){
	int num[30]={0};
	int a;
	for(int i=0; i<28; i++){
		scanf("%d", &a);
		num[a] = a;
	}
	for(int j=1; j<=30; j++){
	if(num[j] == 0) printf("%d\n", j);
	}
}
```
-->과제 안 낸 것은 초기화 된 애들, 그래서 j 출력
--------------------------------  
##8958
---------------------------------
<문제>
"OOXXOXXOOO"와 같은 OX퀴즈의 결과가 있다. O는 문제를 맞은 것이고, X는 문제를 틀린 것이다. 문제를 맞은 경우 그 문제의 점수는 그 문제까지 연속된 O의 개수가 된다. 예를 들어, 10번 문제의 점수는 3이 된다.
"OOXXOXXOOO"의 점수는 1+2+0+0+1+0+0+1+2+3 = 10점이다.
OX퀴즈의 결과가 주어졌을 때, 점수를 구하는 프로그램을 작성하시오.
<입력>
첫째 줄에 테스트 케이스의 개수가 주어진다. 각 테스트 케이스는 한 줄로 이루어져 있고, 길이가 0보다 크고 80보다 작은 문자열이 주어진다. 문자열은 O와 X만으로 이루어져 있다.

-----------------------------------------------------
```ruby
#include <stdio.h>
#include <string.h>
int main(void) { 
    int num, score, sum;
    char test[80];
    scanf("%d", &num);
    for(int i=0; i<num; i++) {
        sum = 0;
        score = 1;
        scanf("%s", test);
        for(int j=0; j<strlen(test); j++) {
            if(test[j] == 'O') {
                sum += score;
                score++;
            }
            if(test[j] == 'X')
                score = 1;
        } 
        printf("%d\n", sum);
    }
}
```
-->변수 선언 해주고, 배열 80개. strlen() 함수는 <string.h> 헤더파일 필요로 함(문자열 길이 반환 함수)
   문자열 O 나오면 1점, 연속으로 나오면 1점 추가 (score++), X 나오면 0점 (score = 1, sum = 0이므로 0점)
