# ctrl404.github.io
애노테이션이 없는 Spring프로젝트.<br>
▶1. 엔터티 클래스:<br>
엔터티 클래스는 주로 Spring 애플리케이션에서 데이터베이스에 저장되는 도메인 객체나 데이터 모델을 나타냅니다. <br>제공된 예제에서 MyEntity 클래스는 엔터티 클래스의 예시입니다.<br>
· 속성/필드: 클래스에는 엔터티의 속성을 나타내는 필드 (id, name, dateColumn)가 포함되어 있습니다.<br>
· 영속성 어노테이션: 현대적인 Spring 애플리케이션에서는 @Entity와 같은 어노테이션을 사용하여 이 클래스가 엔터티임을 나타낼 수 있으며, <br>
클래스와 데이터베이스 테이블 간의 매핑을 구성하는 데 추가적인 어노테이션을 사용할 수 있습니다.<br>
· 캡슐화: 일반적으로 필드는 getter 및 setter 메서드를 사용하여 접근을 제어합니다.<br>
· 직렬화: 특히 분산 환경이나 세션에 저장될 경우, 엔터티 클래스는 Serializable 인터페이스를 구현하는 것이 좋습니다.<br>
<!------------------------------------------------------------------------------------------------------->
package com.example.model;

import java.util.Date;

public class MyEntity {
    private Long id;
    private String name;
    private Date dateColumn;

    // Getter와 Setter 메서드
}
<!------------------------------------------------------------------------------------------------------->
▶2. 빈 클래스:<br>
스프링IoC컨테이너에서 데이터를 관리하고 주입할 수 있도록 하는 Bean.<br>
 XML 설정 파일 작성<br>
<!-- applicationContext.xml -->
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
                           http://www.springframework.org/schema/beans/spring-beans.xsd">

    <!-- MyBean Bean 설정 -->
    <bean id="myBean" class="com.example.beans.MyBean">
        <property name="message" value="Hello, Spring!"/>
    </bean>

</beans><br>
· <beans>: 루트 요소로 Spring Bean 설정을 포함하는 XML 파일을 정의합니다.<br>
· <bean>: 각각의 Bean을 정의합니다. 여기서 id는 해당 Bean을 식별하는 고유한 이름이며, class 속성에는 Bean으로 사용될 클래스의 전체 경로가 포함됩니다.<br>
· <property>: Bean의 속성을 설정합니다. 여기서는 message 속성을 설정하고, 해당 값은 "Hello, Spring!"입니다.<br>
