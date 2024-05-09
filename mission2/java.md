#  자바 
- 자바는 객체지향 언어이다. 
- 이식성이 높다(모든 운영체제에서 실행가능하다.)
- 메모리를 자동으로 관리한다.
#  Hello,world 찍기
<pre>
<code>
 public class Main {
    public static void main(String[] args) {

        System.out.println("hello java");
        System.out.println("hello,world");
    }
}
</code>
</pre>
# 변수 선언하기 
1. 정수형
>  * byte,short,int,long
2.  실수형
> * float,double
3. 문자형
> * char,string(길이 만큼 메모리를 차지 한다.)
4. 논리형 
>boolen,true,false
# 연산자 
1. 산술연산자
> * +,-,*,/,%
2. 증감 연산자
> * ++,--
3. 비교 연산자 
> * ==, !=, >, <, >=,<=
4. 논리연산자
> * &&, ||, !
5. 대입연산자
> * =, +=,-=,*=,/=,%=
* 80~100 점 이면 true가 나오는 프로그램
<pre>
<code>
 public class Main {

    public static void main(String[] args) {

       int score=80;
       boolean result = 80<=score || 100 <= score;
       System.out.println(result);



    }
}
</code>
</pre>
# 조건문 
1. 조건의 참,거짓에 따라 다른 작업을 수행합니다.
2. 주어진 조건을 비교 판단하여 조건에 만족할 경우 지정된 명령을 실행하고,만족하지 않을 경우 다음단계 명령을 수행하도록 한다.
1. if문
> * 아래 처럼 if(조건식) 만약 참이면 성인을 출력 아닐겨우 if을 벗어난다.
```
public class Main {

    public static void main(String[] args) {

        int age=20;
        if (age>=18){
            System.out.println("성인");
        }
       

    }
}
```
2. else
> * if(조건식),else if 에서 만족하는 조건이 없을 떄 실행하는 코드를 제공한다.
```
public class Main {

    public static void main(String[] args) {

        int age=20;
        if (age>=18){
            System.out.println("성인");
        }
        else{
            System.out.println("미성년자");
        }
       

    }
}
```
3. else if
>* 여려개의 조건식을 사용해야 하는 경우 거짓인 조건식들을 건너뛰고 참이 되는 블록을 실행할 수 있다.
```
public class Main {

    public static void main(String[] args) {

        int age=20;
        if (age>=18){
            System.out.println("성인");
        }
        else if (age>=9&&age<=18>){
            System.out.println("미성년자");
        }
        else {
            System.out.println("어린이");
        }
       

    }
}
```
4. switch
> 1. if문을 조금 더 편리하게 사용할 수 있는 기능이다 참고로 if문은 비교연사자를 사용 가능하지만, switch문은 단순히 같은 값이 같으지만 비교 가능하다.
> 2. 조건식의 결과 갑이 case와 일치하면 case의 코드를 실행한다.
>3. break 문은 현재 실행 중인 코드를 끝내고 switch문을 빠져나가게 한다.
>4. default는 if문의 else와 같다.
* 등급의 따라 발급된 쿠폰
```
public class Main {

    public static void main(String[] args) {

        int grade=2;
        int coupon;
        switch (grade){
            case 1:
                coupon=1000;
                break;
            case 2:
                coupon=2000;
                break;
            case 3:
                coupon=3000;
                break;
            default:
                coupon=500;
                break;
        }
        System.out.println("발급받은 쿠폰"+coupon);

    }
}
```
# 반복문
1. while 문
>* while(조건식)이 참이면 코드 블럭을 실행하고, 거짓이면 while문을 벗어난다.
while(조건식)거짓 일때 까지 반복 한다.
```

public class Main {
    

    public static void main(String[] args) {

        int grade=0;
        while (grade<3){
            grade+=1;
            System.out.println("현재 숫자는"+ grade);
        }
        

    }
}
```
2. do while
>* do while 문은 while 과 비슷한 구조 지만 무조건 조건식에 관계없이 무조건 하번을 실행할 수 있다.
```
public class Main {


    public static void main(String[] args) {

        int i=10;
        do{

            i+=1;
            System.out.println("현재 숫자는"+ i);
        }while (i<3);


    }
}
```
3. break,continue
>* break는 반복문을 즉시 종료하고 나간다. continue는 나머지 부분을 건너뛰고 다음 반복으로 진행하는데 사용된다.
4. for
> * for문은 주로 반복 횟수가 정해져 있을 때 사용한다.(for(초기식; 조건식; 증감식))for(;;)은 무한 반복이다.
```
public class Main {


    public static void main(String[] args) {

        int a=5;
        for(int i=1; i<=a; i++)
        {
            for(int j=1; j<=i; j++)
            {
                System.out.print("*");
            }
            System.out.println();
        }


    }
}
```

```
public class Main {


    public static void main(String[] args) {

        int a=5;
        for(int i=1; i<=9; i++)
        {
            for(int j=1; j<=9; j++)
            System.out.println(j+"*"+i+"="+i*j);
        }


    }
}
```
# scope
- 지역변수 란 특정 지역에서만 사용할 수 있는 변수이다.
변수가 선언된 코드블록 ({})안에서는 사용할 수 있지만 여기서 벗어나면 사용하지 못한다.
- scope 란 변수의 접근 가능한 범위 이다ㅣ.
```
public class Main {


    public static void main(String[] args) {

        int a=5;
        for(int i=1; i<=9; i++)
        {
            for(int j=1; j<=9; j++)
            System.out.println(j+"*"+i+"="+i*j);
        }


    }
}
```
* 여기서 a의 scope는 main()전체 이고 i는의 scope는 for()안 이다.
# scope 존재 이유
1. 효율적으로 메모리를 사용할 수 있다.(변수가 필요한 scope에서만 변수를 쓰면 된다.)
2. 코드를 단순하게 할수있다.(필요한scope에서 변수를 쓰지 않고 main에서 변수를 선언해 쓰면 내가 신경써야 할 변수가 하나가 더 생기는데 필요한 scope에 쓰면 이런 일이 안 생긴다.  )
---------------------------------------------------------------------
1. 자동형변환
```
int a=10;
double a=int a;
```
이 과정에서 대입하는 형을 맞춰어야 하기 떄문에 자동으로 int a 에서 double a로 변경된다.
2. 명시적 형변환
> 큰 범위에서 작은 범위 대입은 명시적 형변환이 필요하다.
3. 계산과 형변환
> 서로 다른 타입의 계산은 큰 범위로 자동 형변환이 일어난다.
# scanner
- System.out을 통해 출력을 헀듯이 System.in을 통해 입력을 받을 수 있지만 복잡하다. 이런 문제를 해결하기 위해 자바가 만든 것이 scanner 이다.scanner를 사용하면 간단히 입력 받을 수 있다.
```
scanner.nextline()
```
- 엔터 을 입력할 떄 까지 문자를 가져온다.
```
scanner.nextint()
```
- 정수 입력에 사용한다.
```
scanner.nextDouble()
```
- 실수 입력에 사용된다.
```
import java.util.Scanner;
public class Main {


    public static void main(String[] args) {
        int sum=0;
        int a=0;
        int b=0;
        Scanner scanner=new Scanner(System.in);
        System.out.println("숫자를 입력하세요");
        for (int i=0; i<100; i++)
        {
            a=scanner.nextInt();

            if (a==-1)
            {
                break;
            }
            else{
                sum+=a;
            }
        }
        System.out.println("입력한 수"+sum);

    }
}
```
- scanner를 사용할떄 import java.util.Scanner; 이 것과 Scanner scanner=new Scanner(System.in); 을 사용해야 한다.
# 1 차원배열
- 많은 변수가 있을때 사용하면 변수를 일일히 선언하지 않아도 된다.
1. 기본형
> 변수에 사용할 값을 직접 넣을 수 있는 데이터 타입을 기본형이라 한다.
2. 참조형
> 데이터에 접근하기 위한 주소를 저장하는 데이터 타입을 
참조형 아다.
```
public class Main {


    public static void main(String[] args) {
        int[] sum;
        sum=new int[]{1,2,3,4,5};
        int b=0;
        for (int i=0; i<sum.length; i++)
        {
            System.out.println("입력한 수"+sum[i]);
        }

    }
}
```
# 2차원 배열
- 이름 그대 1차원 배열에서 차원이 더 추가된다. 행과열로 구성된다.
```
public class Main {


    public static void main(String[] args) {
        int[][] sum;
        sum=new int[][]{{1,2,3,4,5},{1,2,3,4,5}};
        int b=0;
        for (int i=0; i<sum.length; i++)
        {
            for (int a=0; a<sum[i].length; a++) {
                System.out.println("입력한 수" + sum[i][a]);
            }
        }

    }
}
```
# 매서드
1. 자바에서의 함수를 메서드라 한다.
2. 기능을 의미한다.
```

import java.util.Scanner;
public class Main {


    public static void main(String[] args) {
        int sum1=add(5,10);
        System.out.println(sum1);

    }
}

public static int add(int a,int b){
    int sum=a+b;
    System.out.println(sum);
    return sum;
}
```
# java 클래스, 객체, 인스턴스
1. 클래스란 객체를 정의한 설계도 또는 틀이라 정의할 수 있다.클래스는 객체를 생성하는데 사용된다.

2. 객체는  속성과 기능을 가지는 프로그램 단위 이다.
- 객채는 속성과 행위(기능)를 가진다. 즉, 클래스를 통해 만들어진 객체가 실제로 사용할 수 있는 주체가 된다.
객체는 상태를  필드로 정하고 동작은 메서드로 할수 있다.
```
Student student1 = new Student();
student1.name = "John";
student1.id = 12345;
student1.major = "Computer Science";
student1.phoneNumber = "123-456-7890";
```
student1는 지금 학생의 상태를 나타내고 있기 떄문에'Student' 클래스의 객체입니다
3. 인스턴스 는 엄밀히 말하면 객체는 모든 인스턴스를 포괄하는 넓은 의미를 가지고 있고 인스턴스는 객체 하나하나를 해당 클래스의 인스턴스라 한다.
```
student1.name = "John";
```
이 것은 객체 중 하나 이기 떄문에 인스턴스 이다.
# 추상 클래스 
- 어느정도의 틀만 갖춘 클래스 를 추상 클래스 라 한다.
- 추상 클래스 는 추상 메서드를 포함 하고 있는데 추상 매서드는  선언부만 작성하고 구현부는 작성하지 않는 것 이다.
- 특정 개발 시점에 내용을 확정지으면 안되거나 계획(틀)만을 세울 때
# 추상 클래스의 특징
- 추상 클래스는 클래스 앞에 abstract 키워드를 이용해서 정의한다.
- 추상 클래스는 미완성의 추상 메소드를 포함할 수 있다.
- 추상 클래스는 인스턴스를 생성할 수 없다.
자체적으로 객체를 생성할 수 없기 떄문에 상속을 통해 자식 클래스에서 인스턴스를 생성해야 한다.
- 추상 클래스를 상속받은 클래스는 추상 클래스가 갖고 있는 추상 메소드를 반드시 구현(Overriding)해야 한다.
- 추상 클래스를 상속받고, 추상 클래스가 갖고 있는 추상 메소드를 구현하지 않으면 해당 클래스도 추상 클래스가 된다.
# 추상 클래스이 목적
- 추상 클래스는 비슷한 동작을 가진 클래스들 사이의 공통된 부분을 추상화하여 표현합니다. 이를 통해 중복되는 코드를 최소화하고 코드의 재사용성을 높일 수 있습니다.
- 코드의 일관성을 유지할 수 있습니다.
- 코드의 유지보수성을 향상시키는 데에 도움을 준다.
