Dưới đây là một ví dụ về bài tập kiểm thử đơn vị với Java. Bài tập này sử dụng JUnit, một framework phổ biến để viết và chạy các bài kiểm thử đơn vị trong Java.

Bài tập: Kiểm thử lớp Calculator
Yêu cầu:

Tạo lớp Calculator với các phương thức sau:

add(int a, int b): Trả về tổng của hai số.
subtract(int a, int b): Trả về hiệu của hai số.
multiply(int a, int b): Trả về tích của hai số.
divide(int a, int b): Trả về thương của hai số (nếu b = 0, ném ra ngoại lệ IllegalArgumentException).
Viết các bài kiểm thử đơn vị cho các phương thức trên sử dụng JUnit 5.

Hướng dẫn:
1. Tạo lớp Calculator
java
Copy code
public class Calculator {

    public int add(int a, int b) {
        return a + b;
    }

    public int subtract(int a, int b) {
        return a - b;
    }

    public int multiply(int a, int b) {
        return a * b;
    }

    public int divide(int a, int b) {
        if (b == 0) {
            throw new IllegalArgumentException("Divider cannot be zero");
        }
        return a / b;
    }
}
2. Viết kiểm thử đơn vị với JUnit
Tạo file CalculatorTest.java để viết kiểm thử:

java
Copy code
import static org.junit.jupiter.api.Assertions.*;
import org.junit.jupiter.api.Test;

public class CalculatorTest {

    @Test
    public void testAdd() {
        Calculator calculator = new Calculator();
        assertEquals(5, calculator.add(2, 3), "2 + 3 should equal 5");
    }

    @Test
    public void testSubtract() {
        Calculator calculator = new Calculator();
        assertEquals(1, calculator.subtract(3, 2), "3 - 2 should equal 1");
    }

    @Test
    public void testMultiply() {
        Calculator calculator = new Calculator();
        assertEquals(6, calculator.multiply(2, 3), "2 * 3 should equal 6");
    }

    @Test
    public void testDivide() {
        Calculator calculator = new Calculator();
        assertEquals(2, calculator.divide(6, 3), "6 / 3 should equal 2");
    }

    @Test
    public void testDivideByZero() {
        Calculator calculator = new Calculator();
        assertThrows(IllegalArgumentException.class, () -> calculator.divide(6, 0), "Dividing by zero should throw IllegalArgumentException");
    }
}
Hướng dẫn chạy kiểm thử:
Thêm thư viện JUnit 5 vào dự án:

Nếu sử dụng Maven, thêm vào file pom.xml:
xml
Copy code
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter</artifactId>
    <version>5.9.3</version>
    <scope>test</scope>
</dependency>
Chạy kiểm thử:

Trong IDE như IntelliJ IDEA hoặc Eclipse, nhấp chuột phải vào file CalculatorTest.java và chọn Run Tests.
Nếu sử dụng Maven, chạy lệnh:
bash
Copy code
mvn test
Mục tiêu:
Hiểu cách viết các bài kiểm thử đơn vị với JUnit.
Biết cách kiểm tra các trường hợp cơ bản và xử lý ngoại lệ.
Hãy thử và thông báo nếu bạn cần hỗ trợ thêm! 😊
