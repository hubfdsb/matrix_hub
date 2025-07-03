# 1. Khái niệm số học và cấu trúc đại số nền tảng

## Các tập số cơ bản

- **Tập số nguyên (Integers), ký hiệu \(\mathbb{Z}\):**  
  Là tập hợp các số nguyên gồm cả số âm, số không, và số dương, ví dụ:  
  $$
  \{ \ldots, -4, -3, -2, -1, 0, 1, 2, 3, 4, \ldots \}
  $$

- **Tập số hữu tỉ (Rational numbers), ký hiệu \(\mathbb{Q}\):**  
  Là tập các số có thể biểu diễn dưới dạng phân số \(\frac{a}{b}\) với \(a, b \in \mathbb{Z}\) và \(b \neq 0\), ví dụ:  
  $$
  \left\{ \ldots, 1, \frac{3}{2}, 2, \frac{22}{7}, \ldots \right\}
  $$

- **Tập số thực (Real numbers), ký hiệu \(\mathbb{R}\):**  
  Bao gồm tất cả các số hữu tỉ và vô tỉ, ví dụ:  
  $$
  \{2, -4, \frac{6}{13}, \pi, \sqrt{2}, \ldots\}
  $$

- **Trường hữu hạn (Finite Fields), ký hiệu \(\mathbb{F}\) hoặc \(\mathbb{Z}_p^*\):**  
  Là tập hữu hạn gồm các phần tử có hai phép toán cộng và nhân, với các phần tử là số nguyên modulo một số nguyên tố \(p\). Mỗi phần tử có phần tử nghịch đảo nhân, tức là phép chia được định nghĩa modulo \(p\).

## Phép toán modulo (Modular Arithmetic)

- **Định nghĩa:**  
  \( n \bmod k \) là phần dư khi chia \(n\) cho \(k\).  
  Ví dụ:  
  $$
  25 \bmod 3 = 1, \quad 15 \bmod 4 = 3
  $$
  Phần dư luôn là số không âm nhỏ hơn \(k\).

- **Lớp tương đương (Equivalence classes):**  
  Các số nguyên được phân thành các lớp tương đương theo modulo \(k\). Ví dụ với \(k=7\), các số 5, 12, 19 đều cùng lớp tương đương vì cùng dư 5 khi chia cho 7.  
  Tập các số được phân thành \(k\) lớp dạng:  
  $$
  i + k\mathbb{Z} = \{ i + k \cdot m \mid m \in \mathbb{Z} \}
  $$
  với \(i = 0, 1, \ldots, k-1\).

- **Ý nghĩa:**  
  Modular arithmetic tạo nền tảng cho các hàm một chiều trong mật mã (one-way functions), vì việc tính modulo dễ nhưng việc tìm số ban đầu từ kết quả modulo là khó (với số lớn).

## Nhóm (Group Theory)

- **Định nghĩa nhóm:**  
  Một nhóm \((G, \cdot)\) gồm tập \(G\) và phép toán nhị phân \(\cdot\) thoả mãn bốn tính chất:
  1. **Tính đóng (Closure):**  
     Với mọi \(a, b \in G\), \(a \cdot b \in G\).
  2. **Tính kết hợp (Associativity):**  
     Với mọi \(a, b, c \in G\),  
     $$
     (a \cdot b) \cdot c = a \cdot (b \cdot c)
     $$
  3. **Phần tử đơn vị (Identity element):**  
     Tồn tại phần tử \(e \in G\) sao cho với mọi \(a \in G\),  
     $$
     e \cdot a = a \cdot e = a
     $$
  4. **Phần tử nghịch đảo (Inverse element):**  
     Với mỗi \(a \in G\), tồn tại \(a^{-1} \in G\) sao cho  
     $$
     a \cdot a^{-1} = a^{-1} \cdot a = e
     $$

- **Nhóm con (Subgroup):**  
  Một tập con của nhóm mà chính nó cũng thoả mãn các tính chất trên.

- **Nhóm tuần hoàn (Cyclic Group) và phần tử sinh:**  
  Nhóm tuần hoàn là nhóm có thể tạo ra bởi một phần tử duy nhất \(g\), tức là các phần tử trong nhóm là lũy thừa của \(g\) và nghịch đảo của nó:  
  $$
  \{g, g^2, g^3, \ldots, g^{-1}, g^{-2}, \ldots\}
  $$  
  Ví dụ: nhóm các số nguyên \((\mathbb{Z}, +)\) với phần tử sinh là 1.

## Trường (Fields)

- **Định nghĩa trường:**  
  Một trường \(F\) là một tập hợp với hai phép toán cộng \((+)\) và nhân \((\cdot)\) thoả mãn các tính chất sau với mọi \(a, b, c \in F\):
  1. **Tính kết hợp:**  
  $$
  a + (b + c) = (a + b) + c, \quad a \cdot (b \cdot c) = (a \cdot b) \cdot c
  $$
  2. **Tính giao hoán:**  
  $$
  a + b = b + a, \quad a \cdot b = b \cdot a
  $$
  3. **Phần tử đơn vị:**  
  Tồn tại \(0, 1 \in F\) sao cho  
  $$
  a + 0 = a, \quad a \cdot 1 = a
  $$
  4. **Phần tử nghịch đảo:**  
  - Với mọi \(a \in F\), tồn tại \(-a\) sao cho \(a + (-a) = 0\).  
  - Với mọi \(a \neq 0\), tồn tại \(a^{-1}\) sao cho \(a \cdot a^{-1} = 1\).
  5. **Phân phối:**  
  $$
  a \cdot (b + c) = a \cdot b + a \cdot c
  $$

- **Trường hữu hạn:**  
  Trường có số phần tử hữu hạn, ví dụ: \(\mathbb{Z}_p\) với \(p\) là số nguyên tố.  
  Trong trường này, phép cộng và phép nhân được thực hiện modulo \(p\).

- **Phần tử sinh trong trường hữu hạn:**  
  Mỗi trường hữu hạn đều có phần tử sinh \(g\) sao cho lũy thừa của \(g\) tạo thành toàn bộ phần tử trong trường (ngoại trừ phần tử 0 trong nhóm nhân).
