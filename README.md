<div align="center">

# ☕ Java: From Zero to Pro

**A complete, hands-on roadmap to learning Java: from your first `Hello, World!` to production-grade architecture.**

![Java](https://img.shields.io/badge/Java-21%2B-ED8B00?style=for-the-badge&logo=openjdk&logoColor=white)
![Level](https://img.shields.io/badge/Level-Beginner%20→%20Pro-success?style=for-the-badge)
![Maven](https://img.shields.io/badge/Build-Maven%20%7C%20Gradle-C71A36?style=for-the-badge&logo=apachemaven&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

*Write once, run anywhere.*

</div>

---

## 📚 Table of Contents

1. [Why Java?](#-why-java)
2. [Learning Path at a Glance](#-learning-path-at-a-glance)
3. [Setup](#-setup)
4. [🟢 Level 1: Beginner](#-level-1-beginner)
5. [🟡 Level 2: Intermediate](#-level-2-intermediate)
6. [🟠 Level 3: Advanced](#-level-3-advanced)
7. [🔴 Level 4: Pro / Expert](#-level-4-pro--expert)
8. [Ecosystem & Tools](#-ecosystem--tools)
9. [Project Ideas](#-project-ideas)
10. [Best Practices](#-best-practices-cheat-sheet)
11. [Resources](#-resources)

---

## 🌟 Why Java?

| Strength | Why it matters |
|---|---|
| **Platform independent** | Compiled to bytecode and run on the JVM on any OS |
| **Strongly typed & safe** | Catches many bugs at compile time |
| **Massive ecosystem** | Spring, Hibernate, Kafka, Android, big data and more |
| **High performance** | JIT compilation, mature garbage collectors |
| **Enterprise standard** | Banking, e-commerce, telecom, cloud-native services |
| **Great job market** | One of the most in-demand languages for decades |

---

## 🗺 Learning Path at a Glance

```
 🟢 BEGINNER          🟡 INTERMEDIATE        🟠 ADVANCED            🔴 PRO
 ───────────          ───────────────        ───────────            ──────
 Syntax               Collections            Concurrency            JVM Internals
 Variables            Generics               Streams & Lambdas      Performance Tuning
 Control Flow    →    Exceptions        →    Modern Java (17-25) →  Design Patterns
 Methods              File I/O               Reflection             Spring Boot / Microservices
 OOP Basics           JDBC & Testing         Networking             Cloud, Docker, K8s
```

> ⏱ **Suggested pace:** Beginner (4–6 wks) → Intermediate (6–8 wks) → Advanced (8–10 wks) → Pro (ongoing)

---

## 🛠 Setup

### 1. Install a JDK
Download an LTS build of **OpenJDK** (e.g., Temurin, Corretto, or Oracle JDK) and verify:

```bash
java -version
javac -version
```

### 2. Pick an IDE
- **IntelliJ IDEA** (recommended)
- **VS Code** + *Extension Pack for Java*
- **Eclipse**

### 3. Your first program

```java
public class HelloWorld {
    public static void main(String[] args) {
        System.out.println("Hello, World! ☕");
    }
}
```

```bash
javac HelloWorld.java   # compile to bytecode
java HelloWorld         # run on the JVM
```

> 💡 Since Java 11 you can run single files directly: `java HelloWorld.java`

---

# 🟢 Level 1: Beginner

**Goal:** Understand the syntax and think in code.

### 1.1 How Java Works
`Source (.java)` → **javac** → `Bytecode (.class)` → **JVM** → `Machine code`

- **JDK** = tools + compiler + JRE
- **JRE** = JVM + libraries
- **JVM** = executes the bytecode

### 1.2 Variables & Data Types

```java
// Primitive types
byte   b = 10;
short  s = 1000;
int    age = 25;
long   population = 8_000_000_000L;
float  pi = 3.14f;
double precise = 3.141592653589;
char   grade = 'A';
boolean isJavaFun = true;

// Reference type
String name = "Ada";

// Type inference (Java 10+)
var city = "Mysuru";
```

### 1.3 Operators

```java
int a = 10, b = 3;
a + b;  a - b;  a * b;  a / b;  a % b;   // arithmetic
a > b;  a == b; a != b;                    // comparison
a > 5 && b < 5;  a > 5 || b > 5;  !true;   // logical
a++;  b--;  a += 5;                        // shorthand
String r = (a > b) ? "a wins" : "b wins";  // ternary
```

### 1.4 Control Flow

```java
// if / else
if (age >= 18) {
    System.out.println("Adult");
} else {
    System.out.println("Minor");
}

// Modern switch expression
String day = switch (3) {
    case 1, 7 -> "Weekend";
    case 2, 3, 4, 5, 6 -> "Weekday";
    default -> "Invalid";
};

// Loops
for (int i = 0; i < 5; i++) System.out.println(i);

int n = 0;
while (n < 3) { n++; }

do { n--; } while (n > 0);

for (String fruit : new String[]{"Apple", "Mango"}) {
    System.out.println(fruit);
}
```

### 1.5 Methods

```java
public static int add(int a, int b) {
    return a + b;
}

// Overloading
public static double add(double a, double b) {
    return a + b;
}
```

### 1.6 Arrays & Strings

```java
int[] nums = {5, 2, 9, 1};
Arrays.sort(nums);
System.out.println(Arrays.toString(nums));   // [1, 2, 5, 9]

int[][] matrix = new int[3][3];              // 2D array

String s = "Java";
s.length();  s.toUpperCase();  s.charAt(0);  s.substring(1, 3);
s.contains("av");  s.replace("a", "o");  String.join("-", "a", "b");

// StringBuilder for efficient concatenation
StringBuilder sb = new StringBuilder();
sb.append("Hello").append(" ").append("World");
```

### 1.7 Object-Oriented Programming (OOP) Basics

```java
public class Person {
    private String name;      // encapsulation
    private int age;

    public Person(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() { return name; }

    public void greet() {
        System.out.println("Hi, I'm " + name);
    }
}

Person p = new Person("Ada", 30);
p.greet();
```

#### The 4 Pillars of OOP

| Pillar | Meaning | Java tool |
|---|---|---|
| **Encapsulation** | Hide data, expose behavior | `private` fields + getters/setters |
| **Inheritance** | Reuse and extend classes | `extends` |
| **Polymorphism** | One interface, many forms | Overriding / overloading |
| **Abstraction** | Show *what*, hide *how* | `abstract` classes, `interface` |

### ✅ Beginner Checklist
- [ ] Write programs using all primitive types
- [ ] Use loops and conditionals confidently
- [ ] Create classes, objects, and constructors
- [ ] Understand `static` vs instance members
- [ ] Debug with your IDE's debugger

---

# 🟡 Level 2: Intermediate

**Goal:** Build real, structured applications.

### 2.1 Inheritance, Interfaces & Abstract Classes

```java
abstract class Shape {
    abstract double area();
    void describe() { System.out.println("Area: " + area()); }
}

class Circle extends Shape {
    private final double r;
    Circle(double r) { this.r = r; }
    @Override double area() { return Math.PI * r * r; }
}

interface Drawable {
    void draw();
    default void print() { System.out.println("Printing..."); }  // default method
}
```

**Key keywords:** `super`, `this`, `final`, `static`, `abstract`, `instanceof`

### 2.2 Exception Handling

```java
try {
    int result = 10 / 0;
} catch (ArithmeticException e) {
    System.err.println("Math error: " + e.getMessage());
} finally {
    System.out.println("Always runs");
}

// try-with-resources (auto-closes)
try (BufferedReader br = new BufferedReader(new FileReader("data.txt"))) {
    System.out.println(br.readLine());
} catch (IOException e) {
    e.printStackTrace();
}

// Custom exception
class InsufficientFundsException extends Exception {
    public InsufficientFundsException(String msg) { super(msg); }
}
```

> **Checked** exceptions (`IOException`) must be handled. **Unchecked** (`RuntimeException`) are optional.

### 2.3 Collections Framework

```
Iterable
 └── Collection
      ├── List   → ArrayList, LinkedList
      ├── Set    → HashSet, LinkedHashSet, TreeSet
      └── Queue  → PriorityQueue, ArrayDeque
Map → HashMap, LinkedHashMap, TreeMap, ConcurrentHashMap
```

```java
List<String> list = new ArrayList<>(List.of("A", "B", "C"));
Set<Integer> set = new HashSet<>(Arrays.asList(1, 2, 2, 3));   // {1, 2, 3}
Map<String, Integer> scores = new HashMap<>();
scores.put("Ada", 95);
scores.getOrDefault("Bob", 0);
scores.merge("Ada", 5, Integer::sum);

for (Map.Entry<String, Integer> e : scores.entrySet()) {
    System.out.println(e.getKey() + " → " + e.getValue());
}
```

| Structure | Best for | Lookup | Ordered |
|---|---|---|---|
| `ArrayList` | Fast index access | O(1) | Insertion |
| `LinkedList` | Frequent insert/delete | O(n) | Insertion |
| `HashMap` | Key-value lookup | O(1) avg | No |
| `TreeMap` | Sorted keys | O(log n) | Sorted |
| `HashSet` | Unique items | O(1) avg | No |

### 2.4 Generics

```java
public class Box<T> {
    private T value;
    public Box(T value) { this.value = value; }
    public T get() { return value; }
}

public static <T extends Comparable<T>> T max(T a, T b) {
    return a.compareTo(b) > 0 ? a : b;
}

// Wildcards
void printAll(List<? extends Number> list) { /* read-only producer */ }
```

### 2.5 Lambdas & Functional Interfaces

```java
Runnable r = () -> System.out.println("Running");
Comparator<String> byLength = (a, b) -> a.length() - b.length();

Function<Integer, Integer> square = x -> x * x;
Predicate<String> isEmpty = String::isEmpty;
Supplier<Double> random = Math::random;
Consumer<String> printer = System.out::println;
```

### 2.6 Streams API

```java
List<String> names = List.of("Ada", "Bob", "Charlie", "Dave");

List<String> result = names.stream()
    .filter(n -> n.length() > 3)
    .map(String::toUpperCase)
    .sorted()
    .collect(Collectors.toList());

int total = IntStream.rangeClosed(1, 100).sum();

Map<Integer, List<String>> byLength =
    names.stream().collect(Collectors.groupingBy(String::length));
```

### 2.7 File I/O (NIO.2)

```java
Path path = Path.of("notes.txt");
Files.writeString(path, "Hello Java");
String content = Files.readString(path);
List<String> lines = Files.readAllLines(path);

try (Stream<Path> files = Files.walk(Path.of("."))) {
    files.filter(Files::isRegularFile).forEach(System.out::println);
}
```

### 2.8 Date & Time API

```java
LocalDate today = LocalDate.now();
LocalDateTime now = LocalDateTime.now();
ZonedDateTime ist = ZonedDateTime.now(ZoneId.of("Asia/Kolkata"));
Duration d = Duration.between(start, end);
String formatted = today.format(DateTimeFormatter.ofPattern("dd MMM yyyy"));
```

### 2.9 Build Tools & Testing

**Maven `pom.xml`**
```xml
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter</artifactId>
    <version>5.10.2</version>
    <scope>test</scope>
</dependency>
```

**JUnit 5 test**
```java
class CalculatorTest {
    @Test
    void addsTwoNumbers() {
        assertEquals(5, new Calculator().add(2, 3));
    }
}
```

### 2.10 JDBC (Databases)

```java
try (Connection con = DriverManager.getConnection(url, user, pass);
     PreparedStatement ps = con.prepareStatement("SELECT * FROM users WHERE id = ?")) {
    ps.setInt(1, 42);
    try (ResultSet rs = ps.executeQuery()) {
        while (rs.next()) System.out.println(rs.getString("name"));
    }
}
```

> ⚠️ Always use `PreparedStatement` to prevent **SQL injection**.

### ✅ Intermediate Checklist
- [ ] Choose the right collection for the job
- [ ] Write generic classes and methods
- [ ] Process data with streams and lambdas
- [ ] Handle exceptions properly
- [ ] Write unit tests with JUnit
- [ ] Manage dependencies with Maven or Gradle

---

# 🟠 Level 3: Advanced

**Goal:** Write concurrent, modern, and idiomatic Java.

### 3.1 Modern Java Features (Java 8 → 25)

```java
// Records (immutable data carriers) – Java 16
public record Point(int x, int y) {}

// Sealed classes – Java 17
public sealed interface Shape permits Circle, Square {}
record Circle(double r) implements Shape {}
record Square(double side) implements Shape {}

// Pattern matching for instanceof and switch – Java 16/21
static double area(Shape s) {
    return switch (s) {
        case Circle c -> Math.PI * c.r() * c.r();
        case Square q -> q.side() * q.side();
    };
}

// Record patterns – Java 21
if (obj instanceof Point(int x, int y)) {
    System.out.println(x + ", " + y);
}

// Text blocks – Java 15
String json = """
    {
      "name": "Ada",
      "role": "Engineer"
    }
    """;

// Optional
Optional<String> opt = Optional.ofNullable(getName());
String upper = opt.map(String::toUpperCase).orElse("UNKNOWN");
```

### 3.2 Multithreading & Concurrency

```java
// Basic thread
Thread t = new Thread(() -> System.out.println("Hello from thread"));
t.start();

// Executor framework
ExecutorService pool = Executors.newFixedThreadPool(4);
Future<Integer> future = pool.submit(() -> 42);
System.out.println(future.get());
pool.shutdown();

// CompletableFuture – async pipelines
CompletableFuture.supplyAsync(() -> fetchUser())
    .thenApply(User::getName)
    .thenAccept(System.out::println)
    .exceptionally(ex -> { ex.printStackTrace(); return null; });

// Virtual threads (Java 21) – lightweight, massively scalable
try (var executor = Executors.newVirtualThreadPerTaskExecutor()) {
    IntStream.range(0, 10_000).forEach(i ->
        executor.submit(() -> {
            Thread.sleep(Duration.ofSeconds(1));
            return i;
        }));
}
```

**Synchronization toolbox**

| Tool | Use case |
|---|---|
| `synchronized` | Simple mutual exclusion |
| `ReentrantLock` | Fine-grained locking, try-lock, fairness |
| `AtomicInteger` | Lock-free counters |
| `ConcurrentHashMap` | Thread-safe map |
| `CountDownLatch` / `CyclicBarrier` | Coordinating threads |
| `Semaphore` | Limiting concurrent access |
| `volatile` | Visibility guarantees |

**Classic pitfalls:** race conditions, deadlocks, starvation, memory visibility. Learn the **Java Memory Model** (happens-before).

### 3.3 Advanced Streams & Collectors

```java
Map<String, Double> avgSalaryByDept = employees.stream()
    .collect(Collectors.groupingBy(
        Employee::dept,
        Collectors.averagingDouble(Employee::salary)));

// Parallel streams (use carefully)
long count = bigList.parallelStream().filter(this::expensiveCheck).count();
```

### 3.4 Reflection & Annotations

```java
@Retention(RetentionPolicy.RUNTIME)
@Target(ElementType.METHOD)
@interface Timed {}

Class<?> clazz = MyService.class;
for (Method m : clazz.getDeclaredMethods()) {
    if (m.isAnnotationPresent(Timed.class)) {
        m.invoke(clazz.getDeclaredConstructor().newInstance());
    }
}
```

> This is how frameworks like Spring and JUnit work under the hood.

### 3.5 Networking & HTTP

```java
HttpClient client = HttpClient.newHttpClient();
HttpRequest request = HttpRequest.newBuilder()
    .uri(URI.create("https://api.example.com/data"))
    .header("Accept", "application/json")
    .GET()
    .build();

HttpResponse<String> response =
    client.send(request, HttpResponse.BodyHandlers.ofString());
System.out.println(response.body());
```

### 3.6 Design Patterns

| Category | Patterns |
|---|---|
| **Creational** | Singleton, Factory, Abstract Factory, Builder, Prototype |
| **Structural** | Adapter, Decorator, Facade, Proxy, Composite |
| **Behavioral** | Strategy, Observer, Command, Template Method, State |

```java
// Builder pattern
Pizza pizza = new Pizza.Builder()
    .size("Large")
    .cheese(true)
    .topping("Olives")
    .build();
```

### 3.7 SOLID Principles

- **S**: Single Responsibility
- **O**: Open/Closed
- **L**: Liskov Substitution
- **I**: Interface Segregation
- **D**: Dependency Inversion

### ✅ Advanced Checklist
- [ ] Use records, sealed types, and pattern matching
- [ ] Build safe concurrent programs
- [ ] Understand `equals`/`hashCode`/immutability deeply
- [ ] Apply common design patterns appropriately
- [ ] Use reflection and annotations
- [ ] Write clean, SOLID code

---

# 🔴 Level 4: Pro / Expert

**Goal:** Build, tune, and ship production systems.

### 4.1 JVM Internals

```
┌─────────────────────── JVM ────────────────────────┐
│  Class Loader  →  Runtime Data Areas  →  Execution │
│                   ┌──────────────┐       Engine     │
│                   │ Heap         │   ┌────────────┐ │
│                   │  ├ Young     │   │ Interpreter│ │
│                   │  └ Old       │   │ JIT (C1/C2)│ │
│                   │ Metaspace    │   │ GC         │ │
│                   │ Thread Stacks│   └────────────┘ │
│                   └──────────────┘                  │
└─────────────────────────────────────────────────────┘
```

**Garbage collectors**

| GC | Best for |
|---|---|
| **G1** (default) | Balanced throughput and latency |
| **ZGC** | Ultra-low pause times, large heaps |
| **Shenandoah** | Low pause, concurrent compaction |
| **Parallel** | Max throughput, batch jobs |

```bash
java -Xms512m -Xmx2g -XX:+UseZGC -jar app.jar
```

### 4.2 Performance Tuning & Profiling

- **Tools:** JFR (Java Flight Recorder), JMC, VisualVM, async-profiler, jcmd, jstack, jmap
- **Benchmarking:** JMH (Java Microbenchmark Harness)
- **Common wins:** avoid needless object creation, right-size collections, use primitives in hot paths, cache wisely, batch I/O, tune GC

```bash
jcmd <pid> GC.heap_info
jstack <pid>                    # thread dump (find deadlocks)
java -XX:+HeapDumpOnOutOfMemoryError -jar app.jar
```

### 4.3 Spring Boot: Production Backend

```java
@SpringBootApplication
public class App {
    public static void main(String[] args) {
        SpringApplication.run(App.class, args);
    }
}

@RestController
@RequestMapping("/api/users")
@RequiredArgsConstructor
class UserController {
    private final UserService service;

    @GetMapping("/{id}")
    public ResponseEntity<UserDto> get(@PathVariable Long id) {
        return ResponseEntity.ok(service.findById(id));
    }

    @PostMapping
    public ResponseEntity<UserDto> create(@Valid @RequestBody CreateUserRequest req) {
        return ResponseEntity.status(HttpStatus.CREATED).body(service.create(req));
    }
}

@Entity
@Table(name = "users")
class User {
    @Id @GeneratedValue(strategy = GenerationType.IDENTITY)
    private Long id;
    private String name;
}

interface UserRepository extends JpaRepository<User, Long> {
    Optional<User> findByEmail(String email);
}
```

**Master these Spring areas:**
`Dependency Injection` · `Spring MVC / WebFlux` · `Spring Data JPA` · `Spring Security (JWT/OAuth2)` · `Actuator` · `Validation` · `Caching` · `Profiles & Config`

### 4.4 Persistence Deep-Dive
- **JPA/Hibernate:** lazy vs eager loading, N+1 problem, caching, transactions, locking
- **Migrations:** Flyway or Liquibase
- **Connection pooling:** HikariCP
- **NoSQL:** MongoDB, Redis, Cassandra

### 4.5 Microservices & Distributed Systems

```
 Client → API Gateway → ┬→ User Service ──→ DB
                        ├→ Order Service ─→ DB
                        └→ Payment Service → DB
                              ↕ Kafka / RabbitMQ (events)
```

- **Patterns:** Service discovery, Circuit Breaker (Resilience4j), Saga, CQRS, Event Sourcing, API Gateway, Outbox
- **Messaging:** Apache Kafka, RabbitMQ
- **Communication:** REST, gRPC, GraphQL
- **Observability:** Micrometer, Prometheus, Grafana, OpenTelemetry, ELK

### 4.6 DevOps & Cloud

```dockerfile
FROM eclipse-temurin:21-jre
WORKDIR /app
COPY target/app.jar app.jar
EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]
```

- **Containers:** Docker, Kubernetes, Helm
- **CI/CD:** GitHub Actions, Jenkins, GitLab CI
- **Cloud:** AWS, Azure, GCP
- **Native images:** GraalVM for fast startup and low memory

### 4.7 Advanced Testing
- **Unit:** JUnit 5, Mockito, AssertJ
- **Integration:** Testcontainers, Spring Boot Test
- **Contract:** Pact
- **Performance:** Gatling, JMeter
- **Quality:** SonarQube, Checkstyle, SpotBugs, JaCoCo

### 4.8 Security
- Validate all input; never trust the client
- Hash passwords with BCrypt/Argon2
- Use HTTPS, JWT/OAuth2, and least privilege
- Keep dependencies patched (OWASP Dependency-Check)
- Avoid insecure deserialization

### 4.9 Architecture
**Clean / Hexagonal Architecture · Domain-Driven Design · Event-Driven Design · 12-Factor Apps · Modular Monoliths**

### ✅ Pro Checklist
- [ ] Read GC logs and heap/thread dumps
- [ ] Profile and fix real bottlenecks
- [ ] Ship a Dockerized Spring Boot service with CI/CD
- [ ] Design resilient, observable microservices
- [ ] Apply DDD and clean architecture
- [ ] Mentor others and review code effectively

---

## 🧰 Ecosystem & Tools

| Area | Tools |
|---|---|
| **IDEs** | IntelliJ IDEA, VS Code, Eclipse |
| **Build** | Maven, Gradle |
| **Frameworks** | Spring Boot, Quarkus, Micronaut, Jakarta EE |
| **Testing** | JUnit 5, Mockito, Testcontainers |
| **ORM** | Hibernate, JPA, jOOQ, MyBatis |
| **Utilities** | Lombok, MapStruct, Jackson, Guava |
| **Mobile** | Android (Kotlin/Java) |
| **Big Data** | Apache Spark, Hadoop, Flink, Kafka |

---

## 💡 Project Ideas

| Level | Project |
|---|---|
| 🟢 | Calculator · Number guessing game · To-do CLI · Tic-Tac-Toe |
| 🟡 | Library management system · Bank app with JDBC · Contact book with file storage · Text-based RPG |
| 🟠 | Multithreaded web crawler · Chat server (sockets) · In-memory cache · Custom dependency-injection mini-framework |
| 🔴 | E-commerce microservices · URL shortener with Redis · Real-time notification system (Kafka) · Distributed rate limiter |

---

## 🏆 Best Practices Cheat Sheet

- ✅ Follow naming conventions: `PascalCase` classes, `camelCase` methods, `UPPER_SNAKE` constants
- ✅ Prefer **immutability** (`final`, records)
- ✅ Program to **interfaces**, not implementations
- ✅ Favor **composition over inheritance**
- ✅ Always override `hashCode` when overriding `equals`
- ✅ Use `try-with-resources` for anything closeable
- ✅ Don't catch `Exception` blindly; never swallow exceptions
- ✅ Use `Optional` for return values, not fields or parameters
- ✅ Prefer `StringBuilder` in loops
- ✅ Write tests first or alongside your code
- ❌ Avoid premature optimization; measure first
- ❌ Avoid returning `null` collections; return empty ones

---

## 📖 Resources

**Books**
- *Effective Java*: Joshua Bloch ⭐
- *Java Concurrency in Practice*: Brian Goetz
- *Clean Code*: Robert C. Martin
- *Head First Java*: Kathy Sierra & Bert Bates (great for beginners)
- *Optimizing Java*: Evans, Gough & Newland

**Online**
- [Dev.java](https://dev.java), the official learning hub
- [Oracle Java Tutorials](https://docs.oracle.com/javase/tutorial/)
- [Baeldung](https://www.baeldung.com), practical guides
- [Spring Guides](https://spring.io/guides)
- [Exercism Java Track](https://exercism.org/tracks/java) and [LeetCode](https://leetcode.com) for practice

---

## 🤝 Contributing

Contributions are welcome! Fork the repo, create a branch, add your improvements, and open a pull request.

## 📄 License

Released under the [MIT License](LICENSE).

---

<div align="center">

**Happy coding! ☕ Keep learning, keep building.**

⭐ If this roadmap helped you, give it a star!

</div>

