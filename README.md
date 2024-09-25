# Download

\* 개인 사용 목적 코어 모듈입니다.

`repositories`에 다음을 추가합니다.

```kotlin
// mavenCentral()을 대체하지 않음.
maven { url = uri("https://jitpack.com") }
```

`dependencies`에 다음을 추가합니다.

```kotlin
// latest version tag: 0.1.0 (if this document is latest version)
implemenation("com.github.merge-simpson:letsdev-jpa-core:0.1.0")
```

# Features

## Super Classes for JPA Entity

### BaseEntity

PK(Primary Key)로 사용할 `id` 컬럼 필드가 `Long` 타입입니다.  
또한 순차적인 자동 증가 필드입니다. (Sequential auto-incrementing integer)

Example:

```java
@Entity
public class ExampleEntity extends BaseEntity {/* id 필드를 추가하지 않아도 됨. */}
```

### UuidBaseEntity

PK(Primary Key)로 사용할 `id` 컬럼 필드가 `java.util.UUID` 타입입니다. 또한 자동 생성 필드입니다.

- `MySQL`의 `binary(16)`
- `H2`, `Postgresql`의 `uuid` (UUID 타입을 사용할 수 있도록 활성화가(enabled) 되어야 합니다.)

Example:

```java
@Entity
public class ExampleEntity extends UuidBaseEntity {/* id 필드를 추가하지 않아도 됨. */}
```