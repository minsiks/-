```c
#include ＜stdio.h＞
int isPrime(int number) { 
  int i; 
  for (i=2; i＜number; i++) { 
    if (number % i == 0) return 0; 
  } 
  return 1; 
} 
 
int main(void) { 
  int number = 13195, max_div=0, i; 
  for (i=2; i＜number; i++) 2639
  if (isPrime(i) == 1 && number % i == 0) max_div = i; 
  printf("%d", max_div); 
  return 0; 
}
```

### 관계 데이터 모델

대절해비

- 관계 대수 - 절차적 어쩌구
- 관계 해석 - 비절차적 어쩌구

### 대칭 키 알고리즘

- IDEA : 국제 데이터 암호화 알고리즘
- SKIPJACK : 미국의 NSA에서 개발 블록 알고리즘

### SOLID

- SRP 단일 책임 원칙 : 소프트웨어의 컴포넌트는 단 하나의 책임만을 가져야 한다.
- OCP 개방 폐쇄 원칙 : 확장에 대해선 열려 있어야 하고 수정에 대해선 닫혀 있어야한다.
- LISP 리츠코프 치환 원칙 : 자식 클래스는 부모클래스에서 가능한 행위를 수행할 수 있어야 한다.
- ISP 인터페이스 분리의 원칙 : 하나의 일반적인 인터페이스 보단 여러 개의 구체적인 인터페이스가 낫다.
- DIP 의존관계 역전 원칙 : 의존 관계를 맺을 때, 변화하기 쉬운것 보단 별화하기 어려운 것에 의존

### 점진적 통합 방식
