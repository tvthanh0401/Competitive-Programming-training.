### Giải bài AtCoder Beginner Contest 074 C
Các bạn có thể xem đề bài ở [đây]([https://atcoder.jp/contests/abc074/tasks/arc083_a](https://atcoder.jp/contests/abc074/tasks/arc083_a))
Tóm tắt đề bài: Người ta muốn tìm cách pha đường vào nước sao cho nồng độ dung dịch đường là tối đa(ở đây đường phải hòa tan toàn bộ trong dung dịch nước). Để làm được việc đó thì ta có 4 thao tác:<br/>
+Cho 100A g nước vào trong dung dịch.<br />
+Cho 100B g nước vào trong dung dịch.<br />
+Cho C g đường vào dung dịch.<br />
+Cho D g đường vào dung dịch.<br />
Người ta cho biết thêm khối lượng dung dịch tối đa cho phép là F g và tối đa E g đường có thể hòa tan trong 100 g nước.
Bài toán yêu cầu cho biết khối lượng dung dịch và khối lượng đường khi nồng độ dung dịch là tối đa theo điều kiện đề bài.<br />
Ta gọi f(i, j) là nồng độ tối đa của dung dịch khi dung dịch có i gam đường và j g (nước + đường). Khi đó, ta thấy rằng f(i, j) sẽ hợp lệ nếu f(i, j - 100B) hoặc f(i, j - 100A) hoặc f(i - d, j - d) hoặc f(i - c, j - c) hợp lệ, và khi nó hợp lệ thì f(i, j) = i / j.<br />
Do bài toán còn có thêm ràng buộc là tối đa E g đường hoàn tan trong 100g nước nên ta sẽ chỉ xét các trường hợp mà f(i, j) <= e / (100 + e).
Đến đây ta có thể giải quyết bài toán bằng kỹ thuật quy hoạch động. Chú ý rằng ta sẽ cho f(0, 0) = 0.5 và chỉ xét các trường hợp i <= j mà thôi.<br />
Độ phức tạp của thuật toán là O(F<sup>2</sup>)
