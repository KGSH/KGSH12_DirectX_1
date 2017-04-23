# 정리 못한것들
Window를 생성하기 위한 5단계
어떤 함수가 어떤 행동을 하는지
윈도우 메모리를 생성하는 함수
키보드
문자

## DirectX에 포함돼 있는 API들 (P. 23)
* Direct3D : 기본 그래픽 API, 3D뿐만 아니라 2D도 지원함
* XACT : 이 API는 여러 WAV파일의 재생과 동시에 재생 특성에 대한 제어를 지원함, 효과음과 음악에 유용
* DirectInput : 조이스틱, 레이싱 휠등 기존 입력장치로부터 입력을 받아옴
* XInput : 윈도우와 Xbox360을 위한 새로운 입력 관련 API임, 윈도우 XP 서비스 팩1 이상부터 동작함,
윈도우에서 Xbox360 컨트롤러를 지원함, Xinput은 기존 DirectInput디바이스에서는 동작 안함
* DirectPlay : 네트워크 통신을 지원하는 API임, 인터넷이나 랜을 통해 다른 플레이어와 연결이 필요한 게임을 만들 수 있게 해준다.
* DirectSetup : 게임을 실행하는 데 필요한 DirectX 런타임의 최종 사용자 설치를 지원하는 편리한 방법을 제공함

## 접근 제어자 (P. 24)
* private : 외부 및 자식(파생) 클래스에서도 접근이 불가능함, 자신만 가능함
* protected : 자식(파생) 클래스, 자신만 접근이 가능함
* public : 자식(파생) 클래스, 외부, 자신 모두 접근 가능함
* C++은 기본적으로 private임
* 이렇게 접근을 제어 하는것을 데이터 은닉(Data Higing), 정보 은닉(Information Hiding)이라고 부름

## 생성자 (P. 25)
* 조건 : 클래스와 동일한 이름, 반환형이 없어야함
* 정의 하지 않을 시 컴파일러에서 디폴트 생성자를 삽입함

## 소멸자 (P.25)
* 조건 : 클래스와 동일한 이름, 반환형이 없어야함, 소멸자 앞에 '~'가 있어야함
* 객체가 소멸될 때 호출
* virtual이 붙으면 가상 소멸자 -> 자식 객체가 파괴시 부모 클래스의 소멸자를 호출함
* 생성자와는 다르게 매개변수를 삽입할 수 없음
* 정의 하지 않을 시 컴파일러에서 디폴트 소멸자를 삽입함

## 가상함수 (P. 28)
* 부모 클래스의 함수를 자식 클래스의 함수에서 재정의 가능함
* 하지만 강제는 아님

## 순수 가상함수 (P.28)
* 자식 클래스에서 꼭 순수 가상함수를 재정의 해야함
* 순수 가상함수가 있는 클래스는 '추상 클래스'가 되어 동적 할당이 불가능 해짐
* 함수 끝에 = 0을 붙여주면됨
* Ex. void init() = 0;

## 예외처리 (P.29)
* try {} : 예외 처리할 부분을 감쌈
* catch {} : 예외 발생시 실행하는 코드를 감쌈
* throw : catch의 인자값을 던짐

## 상속 (P.29)
* 클래스명 옆에 ':'를 붙이고 접근 제한자와 클래스명을 붙이면 됨
* 상속과 접근 지시자의 연관성은 [여기](http://skagh.tistory.com/2)참고하셈 쓰면 너무 길어짐

## 함수 뒤의 const (P.32)
* 그 함수에 속하는 객체 or 변수의 값을 변경 불가

    class Test
    {
      private:
      int \_value = 1;

      public:
      int getValue() const
      {
        //\_value = 2 -> 에러
        return \_value;
      }
    };


## 정리 (P.36)
* C++는 윈도우와 Xbox360 기반의 상용 게임 개발에 주로 사용하는 언어이다.
* 마이크로소프트 비주얼 C++와 마이크로소프트 DirectX API는 중요한 밑천 기술이다.
* 책에 나와 있는 코드를 이해하고 사용하는 데 필요한 프로그래밍 경험의 수준은 객체를 사용하는 방법에 대한 이해와 더불어 C++, C, Java언어에 대한 훌륭한 지식이 필요하다.
* 오늘날 대부분의 상용 게임은 게임 엔진을 사용해서 만들어진다. 여러분은 책을 읽으면서 게임 엔진을 만들어 나갈 것이다.

**아니 씨1발 병신들이 책에 좆같이 이상한거 밖에 안써놈;;**

## 복습문제 (P.37)
1. 2D 컴퓨터 게임의 종류를 두 가지만 말하라 : 퍼즐게임, 타일 기반 게임
2. API란 무엇인가? : Application Programming Interface
3. 게임을 만들 때 DirectX가 제공하는 장점은 무엇인가? : 기존 윈도우 프로그래밍 기술보다 훨씬 더 나은 성능을 가진 윈도우 애플리케이션을 만들 수 있다.(?)
4. 최신 게임 컨트롤러로부터 입력을 받아올 때 사용하는 DirectX API는 무엇인가? : XInput
5. 클래스와 객체 사이의 관계에 대해 설명하라 : 클래스의 선언으로 부터 만들어진 변수가 객체임
6. 클래스의 private부분에 선언돼 있는 항목은 어디에서 접근할 수 있는가? : 클래스 내부에서만
7. 포인터를 통해 객체를 접근할 때 사용하는 C++연산자는 무엇인가? : 간접멤버참조연산자(->)
8. 예외를 처리하는 데 사용하는 코드의 동작 원리는 무엇인가? : throw로 예외를 던지면, std::exception을 상속받은 클래스에서 받은 예외를 처리함
9. WinMerge 프로그램은 무슨 용도로 사용하는가? : 각 파일의 차이를 비교하기 쉬움, 버전관리툴  
10. 컴퓨터 파일을 백업하는 것이 왜 중요한가? : 당연한걸 뭘 물어

## 연습문제 (P.37)
1. 게임 엔진의 목적을 설명하라. : 상용 게임을 만들기 위하여
2. 여러분이 즐겼던 2D 게임 중 일부를 설명하라. : **이래서**
3. 여러분이 만들고 싶은 2D 게임을 설명하라. : **이책이**
4. 게임을 재밌게 만들어주는 요소에는 주로 무엇이 있는가? : **좆병신 책인거임**

## WinAPI를 사용하기 위해 include해야하는 헤더파일 (P.44)
* windows.h

## WinMain함수 (P.43 ~ 45)
* 윈도우 프로그래밍에서 main이 WinMain함수이다.
* 반환형은 int임 반환되는 값은 wParam 매개변수에 저장돼 있는 값을 반환한다.
* 메세지 루프 진입 전에 WinMain이 종료되면 0을 반환함
* 매개변수들
  * hInstance : 기본적으로 애플리케이션에 관한 포인터다. 어느 애플리케이션이 호출됐는지 식별해야 하는 일부 윈도우 함수에서 사용한다.
  * hPrevInstance : 항상 NULL이다. 이전 버전의 윈도우 호환성만을 위해 존재하는 쓸모없는 매개변수다.
  * lpCmdLine : 커맨드라인 매개변수에 대해 NULL로 꿑너눈 문자열울 가리키는 포인터이다. 커맨드라인 매개변수는 애플리케이션이 실행될 때 전달되는 단어나 기호다.
  * mCmdShow : 윈도우를 어떻게 보여줄 것인지 설정한다.
* 일반적으로 윈도우의 모습을 제어하는 데는 위의 매개변수들은 안씀

## Window클래스 구조체 매개변수들 (P.47)
* cbSize : 구조체의 크기를 나타낸다. (주로 sizeof(구조체)로 대입함)
* style : 윈도우를 갱신하는 방법을 포함해 윈도우에 대한 다양한 측면을 정의한다. 스타일은 '|'인 or연산으로 결합한다.
* lpfnWndProc : 윈도우에 보낸 메세지를 처리하는 함수를 가리키는 포인터다.
* cbClsExtra : Window클래스를 위해 시스템에서 확보해야 하는 여분의 메모리를 지정한다.
* hInstance : 클래스를 등록한 애플리케이션을 식별한다
* hIcon : 윈도우에서 사용할 프로그램을 상징하는 큰 아이콘을 정의한다.
* hCursor : 윈도우에서 사용할 마우스 커서를 정의한다.
* hbrBackground : 윈도우의 배경을 채우는 데 사용하는 색, 패턴을 정의함
* lpszMenuName : 스스로 정의하지 않는 윈도우의 기본 메뉴를 정의한다.
* hIconsm : 윈도우의 제목 표시줄과 시작 메뉴에 사용할 작은 아이콘을 정의한다.
* RegisterClassEx : RegisterClassEx()를 호출해 클래스를 등록할 수 있다.

## 클래스 구조체를 등록할 때 사용하는 함수 (P.47)
* RegisterClassEx : RegisterClassEx()를 호출해 클래스를 등록할 수 있다.

## 디바이스 컨텍스트(DC) (P.58)
* 윈도우는 다양한 표시 장치나 출력 장치와 동작할 수 있게 설계돼 있다.
* 위와 같은 장치독립성이 같은 애플리케이션이 다양한 출력 장치에 접근할 수 있게 해준다.
* 그 장치독립성의 핵심이 GDI(Graphics Device Interface)다. GDI는 DLL(Dynamic Link Library)로, 디바이스 드라이버와 함께 애플리케이션이 프린터나 VGA화면에 그릴 수 있게 해준다.
* DC는 Graphics객체와 속성을 정의하는 구조체이다. 윈도우 운영체제는 윈도우를 생성할 때 DC를 만든다.

## WM_CHAR 메세지 (P.58)
* 윈도우는 키 누름과 관련된 몇 가지 메세지를 보냄
* 메시지를 읽기 위해 WM_CHAR를 사용함, 읽기 위해서는 WinProc함수에 WM_CHAR메세지 핸들러만 추가하면됨

        case WM_CHAR
        {
          switch(wParam)
          {
            case 0x08: //백스페이스
            case 0x09: //탭
            case 0x0A: //라인피드
            ...
          }
        }

## 키보드

## 뮤텍스 (P.70)
* 한 번에 하나의 스레드만 소유할 수 있는 객체다.
* CreateMutex함수를 호출해 생성가능하다.

        bool AnotherInstance()
        {
          HANDLE ourMutex;
          ourMutex = CreateMutex(NULL, true, "Use_a_duffernt_string_here_for_each_program_48161_XYZZY");
          if (GetLastError() == ERROR_ALREADY_EXISTS)
            return true;
          return false;
        }

## 윈도우에서의 멀티 태스킹 (P.71)
* 크게 타임 슬라이싱 or 선점형 멀티태스킹이 있다.
* 타임 슬라이스 : 하나의 스레드를 시작하면 아주 짧은 시간 동안 실행하고 이 과정을 모든 스레드에 반복
* 일반적으로 슬라이스 시간은 1/20밀리초
* 일반적인 윈도우 시스템에서 주어진 시간에 수십 개의 스레드가 실행되므로, 선점형 멀티 태스킹은 여전히 필요함
* 윈도우의 멀티태스킹 특징은 짧은 타임 슬라이스에서만 실행이 허용됨
* 다음 타임 슬라이스가 발생할 때에 대한 매우 제한된 통제를 가짐
