---


---

<h3 id="giải-bài-atcoder-beginner-contest-053d">Giải bài Atcoder Beginner Contest 053D</h3>
<p>Các bạn có thể xem đề bài ở <a href="https://atcoder.jp/contests/arc068/tasks/arc068_b">đây</a><br>
Mình tóm tắt qua một chút đề bài: Ta sẽ có <em><strong>N</strong></em> lá bài,  mỗi lá bài có ghi 1 số tự nhiên <em>i</em>. Ta sẽ thực hiện thao tác sau để các lá bài còn lại sẽ khác nhau từng đôi một:<br>
Thao tác: Lấy 3 lá tùy chọn, bỏ đi 2 lá có số ghi trên các lá bài là nhỏ nhất và lớn nhất.<br>
Yêu cầu là chúng ta sẽ đưa số lá bài khác nhau lớn nhất có thể từ điều kiện đề bài đã cho.<br>
Điều đầu tiên chúng ta cần phải làm đó là đếm số lượng các lá bài có số ghi giống nhau trong N lá bài đã cho. Chúng ta sẽ lưu lại số lượng các lá bài chỉ xuất hiện một lần duy nhất. Với các lá bài còn lại, ta sẽ phát hiện ra điều sau:<br>
Với lá bài <em>i</em>, xuất hiện <em>2k</em> lần, ta có thể giảm số lần xuất hiện của nó còn lại 2 bằng cách thực hiện thao tác như đề bài đã cho. Ta sẽ lưu số lượng lá bài xuất hiện 2 lần sau khi thực hiện biến đổi trên bằng biến <strong>twos</strong>.<br>
Với các lá bài j, xuất hiện <em>2k + 1</em> lần thì ta sẽ giảm số lần xuất hiện còn lại 1 cũng bằng thao tác trên. Số lượng các lá j như thế này sẽ được cộng vào số lượng lá bài chỉ xuất hiện 1 lần mà ta đã tính ở trên. Ta gọi biến để lưu giá trị này là <strong>ones</strong>.<br>
<em>Ta sẽ chỉ quan tâm với biến twos, nếu twos chẵn thì ta có thể biến tất cả các lá thuộc nhóm này thành các lá thuộc nhóm xuất hiện 1 lần. Kết quả bài toán khi đó sẽ là <strong>ones + twos</strong>.<br>
Nếu twos lẻ, ta sẽ phải hi sinh 1 lá thuộc nhóm ones, khi đó kết quả sẽ là <strong>twos + ones - 1</strong>.</em><br>
<strong>Chẳng hạn ví dụ đề bài đã cho:</strong><br>
1 2 1 3 7<br>
Ta thấy twos = 1, nhóm này chỉ có mỗi {1}.<br>
Ta có ones = 3, nhóm này gồm {2, 3, 7}. Khi đó ta buộc phải hi sinh 1 lá thuộc nhóm ones. Khi đó kết quả là ones + twos - 1.<br>
<strong>Ví dụ 2:</strong><br>
1 3 5 2 1 3 2 8 8 6 2 6 11 1 1<br>
Ta có ones = 3, {2, 5, 11}<br>
ta có twos = 4, {1, 3, 6, 8}. Ta có thể lấy 2 lá 1 + 1 lá 3, sau thao tác này ta sẽ còn 1 lá 1 và 1 lá 3. Tương tự ta lấy 2 lá 6 và 1 lá 8, sau thao tác này ta còn 1 lá 6 và 1 lá 8. Như vậy với twos chẵn, ta sẽ luôn biến được tất cả các lá thuộc nhóm này thành các lá thuộc nhóm chỉ xuất hiện 1 lần. Kết quả trong trường hợp này là ones + twos.</p>

