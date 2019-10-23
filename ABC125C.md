### Giải bài Atcoder Beginner Contest 125 C

Các bạn có thể xem đề bài toán ở [đây](https://atcoder.jp/contests/abc125/tasks/abc125_c).<br />
Tóm tắt đề bài:<br />
Cho N số tự nhiên, chúng ta sẽ chọn 1 trong N số đó và thay thế bằng 1 số khác sao cho ước chung lớn nhất của N số sau khi đã thay đổi số trên là lớn nhất.<br />
Ta có thể thấy để giải quyết bài toán trên thì ý tưởng là ta sẽ chọn lần lượt các số trong N số trên, và thay thế số đó bằng ước chung lớn nhất của tất cả các số còn lại. Bài toán tương đương với việc **bỏ đi 1 số trong N số trên và tính ước chung lớn nhất của các số còn lại, ta sẽ tìm sao cho UCLN đó là max**.<br />
Ta có:<br />
**kết quả bài toán = max<sub>i</sub> gcd(gcd(a<sub>0</sub>, a<sub>1</sub>..., a<sub>i-1</sub>), gcd(a<sub>i+1</sub>, a<sub>i+2</sub>,...,a<sub>n-1</sub>))**(1)<br />
Đến đây ta thấy rằng ta sẽ phải tính gcd của các số từ số thứ 0 đến i-1 và từ i+1 đến n-1 cho tất cả các i, nếu dùng vòng lặp thì thì ta sẽ có thuật toán với độ phức tạp O(N<sup>2</sup>logN). Hiển nhiên sẽ bị TLE với điều kiện mà bài toán đưa ra.<br />
Tuy nhiên từ (1), ta nhận ra rằng ta có thể tính sẵn gcd từ các số thứ 0 đến j và từ j đến n - 1 sẵn:<br />
+Gọi P1(j) là gcd của các số từ thứ 0 đến j, ta có:<br />
P1(j) = gcd(P1(j-1), a<sub>j</sub>)<br />
Như vậy ta có thể dùng 1 mảng để lưu trữ các giá trị này.<br />
+Tương tự P2(j) là gcd các số từ thư j đến n - 1:<br />
P2(j) = gcd(P2(j+1), a<sub>j</sub>) <br />
Đến đây ta sẽ thay đổi công thức (1) thành: <br />
**kết quả bài toán = max<sub>i</sub> gcd(P1(i-1), P2(i+1))** (2)<br />
Như vậy lúc này độ phức tạp của thuật toán sẽ giảm xuống còn O(NlogN). <br />
Ta giải quyết xong bài toán. <br />
