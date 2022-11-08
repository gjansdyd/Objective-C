# Basic Syntax

# 선언부와 구현부

# 선언부와 구현부

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

## 선언부

위의 설명에 따라 실제 코드는 다음과 같이 작성할 수 있다.

```objectivec
**// Vehicle_1.h**
#import <Foundation/Foundation.h>

@interface Vehicle : NSObject {
    int wheels; 
    int seats;
}

-(void) setWheels: (int)w;
-(void) setSeats: (int)s;
-(void) wheels;
-(void) seats;

@end
```

 만약 **Properties Control Access(@property)**를 사용한다면  위의 코드는 다음으로 대체될 수도 있다.

```objectivec
**// Vehicle_2.h: Vehicle_1.h와 동일한 기능을 한다.**
#import <Foundation/Foundation.h>

@interface Vehicle : NSObject {
}

@property int wheels;
@property int seats;
@end
```

 

 위의 @property는 자동으로 getter와 setter를 만들어준다. 이 때 만들어지는 함수의 이름은 “Vehicle_1.h”에서 선언된 함수와 같다. 만약 Properties Control Access를 사용하며 동시에 getter와 setter함수명을 재정의 하고 싶다면 다음과 같이 쓸 수도 있다.

```objectivec
**// Vehicle_3.h: Vehicle_1.h, Viehicle_2와 동일한 기능을 한다.**
#import <Foundation/Foundation.h>

@interface Vehicle : NSObject {
}

@property (getter=getWheelsValue, setter=setWheelsValue:) int wheels;
@property (getter=getSeatsValue, setter=setSeatsValue:) int seats;
@end
```

## 구현부

 구현부의 실제 코드는 다음과 같이 작성한다

```objectivec
**// Vehicle.m 파일**
#import <Foundation/Foundation.h> // Apple에서 기본 제공하는 애들은 꺽쇠
#import "Vehicle.h" // 본인이 직접 만든 건 쌍따옴표 사용. 
										// 보통 1header-1method. 둘의 이름은 같고 확장자는 다름.

@implementation Vehicle // method파일의 시작을 의미.
// setter
-(void) setWheels: (int)w {
    wheels = w;
}
-(void) setSeats: (int)s {
    seats = s;
}

// getter
-(int) wheels {
    return wheels;
}
-(int) seats {
    return seats;
}

@end
```

parameter가 2개 이상인 함수는 다음과 같이 선언하고 구현한다.

```objectivec
**// Test.h**
@interface Test: NSObject {
	int value1;
	int value2;
}

-(void)setWheels:(int)w Seats:(int)s; 
			// parameter 2개 받을 때에는 위와 같이 사용
			// "**:"표시? 파라미터를 구분하는 단위**
@end

**// Test.m**
#import <Foundation/Foundation.h> 
#import "Test.h"

@implementation Test // method파일의 시작을 의미.
-(void)setWheels:(int)w Seats:(int)s {
    wheels = w;
    seats = s;
}

@end
```
