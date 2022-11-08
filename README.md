# 0. Basic Syntax

Objective-C는 크게 선언부와 구현부로 나누어 코드를 작성한다.
먼저 선언부는 다음과 같이 작성한다.

```objectivec
// 꺽쇠 헤더는 Apple에서 제공하는 것
// 사용자 정의 헤더는 ""(쌍따옴표) 사용
#import <Foundation/Foundation.h> 

@interface 클래스명: 상속받을_클래스 {
	// member variable 
	자료형 변수명; // 여기서 값을 바로 초기화할 수 없다
}

-(리턴타입) 함수명: (자료형)함수내_변수명;
@end
```

구현부는 다음과 같이 작성한다.

```objectivec
// 선언부가 적힌 헤더를 추가한다
#import "선언부헤더.h"

@implementation 클래스명
-(리턴타입) 함수명: (자료형)함수내_변수명 {
	//처리할 내용 기재
}
@end 

// Command line tool로 실행해야 하므로 최종적으로는 이 함수를 통해 실행된다.
int main(int argc, const char * argv []) {
	//선언부+구현부의 클래스를 호출함
}
```
