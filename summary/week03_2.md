# 스프링 빈 설정 메타 정보: BeanDefinition

#### 스프링이 다양한 설정 형식을 지원할 수 있는 중심에는 "BeanDefinition"이라는 추상화가 있다.
- 역할과 구현을 개념적으로 나눈 것
- XML을 읽어서 BeanDefinition을 만들면 된다.
- 자바 코드를 읽어서 BeanDefinition을 만들면 된다.
- `@Bena`, `<bean>` 당 각각 하나씩 메타 정보가 생성된다.
- 스프링 컨테이너는 이 메타정보를 기반으로 스프링 빈을 생성한다.
<br>

#### BeanDefinition 정보
- `BeanClassName`: 생성할 빈의 클래스 명 (자바 설정처럼 팩토리 역할의 빈을 사용하면 없음)
- `factoryBeanName`: 팩토리 역할의 빈을 사용할 경우의 이름 (예: appConfig)
- `factoryMethodName`: 빈을 생성할 팩토리 메서드 지정 (예: memberService)
- `Scope`: 싱글톤(기본값)
- `lazyInit`: 빈의 생성을 스프링 컨테이너 생성시가 아닌 실제 빈 사용시까지 최대한 지연처리 하는지 여부
- `InitMethodName`: 빈을 생성하고, 의존관계를 적용한 뒤에 호출되는 초기화 메서드 명
- `DestroyMethodName`: 빈의 생명주기가 끝나서 제거하기 직전에 호출되는 메서드 명
- `Constructor arguments`, `Properties`: 의존관계 주입에서 사용 (자바 설정처럼 팩토리 역할의 빈을 사용하면 없음)
