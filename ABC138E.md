### Giải bài Atcoder Beginner Contest 138 E
Các bạn có thể xem đề bài ở [đây](https://atcoder.jp/contests/abc138/tasks/abc138_e) <br />
Với bài này thì ý tưởng là chúng ta sẽ duyệt qua xâu s 1 lần và lưu lại vị trí của các ký tự. Chẳng hạn: <br />
s = 'abaacz' <br />
Khi đó pos[a] = {0, 2, 3} <br />
Tương tự pos[b] = {1}, pos[c] = {4} và pos[z] = {5}. <br />
Khi đó ta khởi tạo index = 0, bắt đầu duyệt xâu t, ứng với ký tự kt nào đó thuộc t thì ta sẽ dùng thuật toán tìm kiếm nhị phân để tìm vị trí phù hợp cho ký tự đó: <br />
ví dụ curr = upperbound(pos[kt], index), khi đó vị trí của kt sẽ là pos[kt][curr] nếu curr <= len(pos[kt]) - 1, ngược lại thì là pos[kt][0] <br />
index sau đó sẽ được thay đổi bằng (pos[kt][curr] + 1) % len(s) <br />
Tương tự như vậy ta sẽ tìm được tất cả các vị trí phù hợp cho các kí tự còn lại trong t <br />

