### **Một bài tổ hợp hay**.
 Tình cờ làm một bài dễ trên hackerearth, các bạn có thể tham khảo tại [đây](https://www.hackerearth.com/practice/math/combinatorics/basics-of-combinatorics/practice-problems/algorithm/win-the-game-33/)</br>
**Tóm tắt đề bài**: Cho số <img src="https://tex.s2cms.ru/svg/N" alt="N" />, bài toán yêu cầu ta tính số lượng các số chẵn và số lượng các số lẻ trong dãy <img src="https://tex.s2cms.ru/svg/%5Cbinom%7Bn%7D%7B0%7D" alt="\binom{n}{0}" />, <img src="https://tex.s2cms.ru/svg/%5Cbinom%7Bn%7D%7B1%7D" alt="\binom{n}{1}" />, ..., <img src="https://tex.s2cms.ru/svg/%5Cbinom%7Bn%7D%7Bn%7D" alt="\binom{n}{n}" />.</br>
**Số lượng test**: <img src="https://tex.s2cms.ru/svg/1%20%5Cleq%20T%20%5Cleq%20100000" alt="1 \leq T \leq 100000" />. </br>
**Ràng buộc**: <img src="https://tex.s2cms.ru/svg/1%20%5Cleq%20N%20%5Cleq%2010%5E9" alt="1 \leq N \leq 10^9" />.</br>
**Time limit**: 0.2 s.</br>
Điều đầu tiên, các bạn không hề nhìn nhầm, số lượng test lên đến 100000 và N lớn đến <img src="https://tex.s2cms.ru/svg/10%5E9" alt="10^9" /> do đó việc tính từng số hạng trong dãy rồi sau đó kiểm tra tính chẵn lẻ là điều không thể. Tuy nhiên rất may, ở phần bình luận, có 1 bạn đã gợi ý rằng số lượng các số lẻ trong dãy trên sẽ bằng <img src="https://tex.s2cms.ru/svg/2%5Ek" alt="2^k" /> trong đó <img src="https://tex.s2cms.ru/svg/k" alt="k" /> là số lượng các bit 1 trong biểu diễn nhị phân của số <img src="https://tex.s2cms.ru/svg/N" alt="N" />. Khi đó số lượng số chẵn là <img src="https://tex.s2cms.ru/svg/(N%20%2B%201)%20-%202%5Ek" alt="(N + 1) - 2^k" />. Bài toán có thể giải quyết với độ phức tạp <img src="https://tex.s2cms.ru/svg/O(TlogN)" alt="O(TlogN)" />. </br>
Chúng ta sẽ tìm cách chứng minh điều trên là đúng. Đầu tiên ta có định lý sau: </br>
**Định lý**: Cho 2 số nguyên không âm <img src="https://tex.s2cms.ru/svg/n" alt="n" /> và <img src="https://tex.s2cms.ru/svg/k" alt="k" />, khi đó ta có:</br>
<img src="https://tex.s2cms.ru/svg/%5Cbinom%7Bn%7D%7Bk%7D%20%5Cequiv%200%20" alt="\binom{n}{k} \equiv 0 " /> (mod 2) nếu n chẵn và k lẻ. </br>
<img src="https://tex.s2cms.ru/svg/%5Cbinom%7Bn%7D%7Bk%7D%20%5Cequiv%20%5Cbinom%7B%5Cfrac%7Bn%7D%7B2%7D%7D%7B%5Cfrac%7Bk%7D%7B2%7D%7D" alt="\binom{n}{k} \equiv \binom{\frac{n}{2}}{\frac{k}{2}}" /> (mod 2) cho các trường hợp còn lại. </br>
Để chứng minh định lý trên, ta xét 4 trường hợp:</br>
1. **n chẵn và k lẻ**:</br>
Ta có:</br>
<img src="https://tex.s2cms.ru/svg/k%20%5Cbinom%7Bn%7D%7Bk%7D%20%3D%20n%20%20%5Cbinom%7Bn%20-%201%7D%7Bk%20-%201%7D" alt="k \binom{n}{k} = n  \binom{n - 1}{k - 1}" /> (*)</br>
Khi đó dễ thấy <img src="https://tex.s2cms.ru/svg/%5Cbinom%7Bn%7D%7Bk%7D" alt="\binom{n}{k}" /> chẵn.
2.  **n chẵn và k chẵn**:</br>
Khi đó ta có: </br>
<img src="https://tex.s2cms.ru/svg/%5Cbinom%7Bn%7D%7Bk%7D%20%3D%20%5Cfrac%7Bn(n%20-%201)(n%20-%202)...(n%20-%20k%20%2B%201)%7D%7B1%5Ccdot2%5Ccdot3...%5Ccdot%20k%7D" alt="\binom{n}{k} = \frac{n(n - 1)(n - 2)...(n - k + 1)}{1\cdot2\cdot3...\cdot k}" /></br>
Ta gom các số chẵn và số lẻ lại với nhau:</br>
<img src="https://tex.s2cms.ru/svg/%5Cbinom%7Bn%7D%7Bk%7D%20%3D%20%5Cfrac%7B(n%20-%20k%20%2B%201)(n%20-%20k%20%2B%203)...(n%20-%201)%7D%7B1%5Ccdot3%5Ccdot5...%5Ccdot%20(k%20-%201)%7D%20%5Ccdot%20%5Cfrac%7B(n%20-%20k%20%2B%202)(n%20-%20k%20%2B%204)...(n%20-%202)n%7D%7B2%5Ccdot4%5Ccdot6...%5Ccdot%20k%7D" alt="\binom{n}{k} = \frac{(n - k + 1)(n - k + 3)...(n - 1)}{1\cdot3\cdot5...\cdot (k - 1)} \cdot \frac{(n - k + 2)(n - k + 4)...(n - 2)n}{2\cdot4\cdot6...\cdot k}" /></br>
Ta lại có:</br>
<img src="https://tex.s2cms.ru/svg/%5Cfrac%7B(n%20-%20k%20%2B%202)(n%20-%20k%20%2B%204)...(n%20-%202)n%7D%7B2%5Ccdot4%5Ccdot6...%5Ccdot%20k%7D%20%3D%20%5Cfrac%7B2%5Ek%20%5Ccdot%20(n%2F2%20-%20k%2F2%20%2B%201)(n%2F2%20%2B%20k%2F2%20%2B%202)...n%2F2%7D%7B2%5Ek%20%5Ccdot%201%5Ccdot2...%5Ccdot%20k%2F2%7D%20%3D%20%5Cbinom%7Bn%2F2%7D%7Bk%2F2%7D" alt="\frac{(n - k + 2)(n - k + 4)...(n - 2)n}{2\cdot4\cdot6...\cdot k} = \frac{2^k \cdot (n/2 - k/2 + 1)(n/2 + k/2 + 2)...n/2}{2^k \cdot 1\cdot2...\cdot k/2} = \binom{n/2}{k/2}" /></br>
Vậy suy ra:</br>
<img src="https://tex.s2cms.ru/svg/%5Cbinom%7Bn%7D%7Bk%7D%20%5Cequiv%20%5Cbinom%7Bn%2F2%7D%7Bk%20%2F%202%7D" alt="\binom{n}{k} \equiv \binom{n/2}{k / 2}" /> (mod 2) nếu n chẵn và k chẵn. (**)</br>
3. **n lẻ và k lẻ**:</br>
Sử dụng (*) và (**), ta có ngay điều cần chứng minh.
4. **n lẻ và k chẵn**:</br>
Ta có <img src="https://tex.s2cms.ru/svg/(n%20-%20k)%20%5Ccdot%20%5Cbinom%7Bn%7D%7Bk%7D%20%3D%20(n%20-%20k)%20%5Ccdot%20%5Cbinom%7Bn%7D%7Bn%20-%20k%7D" alt="(n - k) \cdot \binom{n}{k} = (n - k) \cdot \binom{n}{n - k}" /> và <img src="https://tex.s2cms.ru/svg/(n%20-%20k)%5Cbinom%7Bn%7D%7Bn%20-%20k%7D%20%3D%20n%5Cbinom%7Bn%20-%201%7D%7Bn%20-%20k%20-%201%7D%20%3D%20n%5Cbinom%7Bn%20-%201%7D%7Bk%7D" alt="(n - k)\binom{n}{n - k} = n\binom{n - 1}{n - k - 1} = n\binom{n - 1}{k}" /></br>
Lúc này ta áp dụng trường hợp 2. Để ý vì n lẻ nên n / 2 = (n - 1) / 2 (chia nguyên). </br>

Như vậy, để kiểm tra tính chẵn lẻ của <img src="https://tex.s2cms.ru/svg/%5Cbinom%7Bn%7D%7Bk%7D" alt="\binom{n}{k}" />, ta có thể sử dụng định lý trên cho đến khi xuất hiện tham số phía trên là số chẵn và tham số phía dưới là số lẻ, hoặc tham số phía dưới bằng 0.</br>
**Chúng ta xét ví dụ sau**:</br>
<img src="https://tex.s2cms.ru/svg/185_%7B10%7D%20%3D%2010111001_%7B2%7D" alt="185_{10} = 10111001_{2}" /></br>
<img src="https://tex.s2cms.ru/svg/165_%7B10%7D%20%3D%2010100101_%7B2%7D" alt="165_{10} = 10100101_{2}" /></br>
Ta sẽ xét các bit của 2 số trên từ phải sang trái, ta sẽ tìm các vị trí xuất hiện bit 0 ở số 185 và so sánh với bit tương ứng ở số 165. Ta thấy rằng ở bit <img src="https://tex.s2cms.ru/svg/2%5E1" alt="2^1" />, 2 bit giống nhau và bằng 0 nên ta tiếp tục đến vị trí bit <img src="https://tex.s2cms.ru/svg/2%5E2" alt="2^2" />. Tại đây phía trên bit 0(tương ứng với số chẵn) và phía dưới bit 1(ứng với số lẻ), tương ứng với trường hợp thứ nhất trong định lý, do đó ta kết luận ngay <img src="https://tex.s2cms.ru/svg/%5Cbinom%7B185%7D%7B165%7D" alt="\binom{185}{165}" /> là số chẵn.</br>
**Ví dụ khác**:</br>
<img src="https://tex.s2cms.ru/svg/75_%7B10%7D%20%3D%201001011_%7B2%7D" alt="75_{10} = 1001011_{2}" /></br>
<img src="https://tex.s2cms.ru/svg/11_%7B10%7D%20%3D%200001011_%7B2%7D" alt="11_{10} = 0001011_{2}" /></br>
Ở ví dụ này, ta thấy rằng ở dưới, sau 6 lần chia thì tham số k lúc này bằng 0, và n lẻ, nên <img src="https://tex.s2cms.ru/svg/%5Cbinom%7B75%7D%7B11%7D" alt="\binom{75}{11}" /> là số lẻ.</br>
Đến đây, ta có nhận xét sau: Nếu <img src="https://tex.s2cms.ru/svg/%5Cbinom%7Bn%7D%7Bk%7D" alt="\binom{n}{k}" /> là số lẻ thì tại các vị trí bit 0 của n thì các bit của k ở vị trí tương ứng cũng sẽ bằng 0(Nếu các bit của k bằng 1 thì theo trường hợp 1 của định lý trên ta sẽ rút ra được <img src="https://tex.s2cms.ru/svg/%5Cbinom%7Bn%7D%7Bk%7D" alt="\binom{n}{k}" /> lẻ). Tại các vị trí bit 1 của n thì các bit của k có thể nhận giá trị 0 hoặc 1. Vậy ta có định lý sau:</br>
**Định lý**: Số lượng các số lẻ ở hàng thứ <img src="https://tex.s2cms.ru/svg/n" alt="n" /> của tam giác Pascal bằng <img src="https://tex.s2cms.ru/svg/2%5Ew" alt="2^w" />, trong đó <img src="https://tex.s2cms.ru/svg/w" alt="w" /> là số lượng bit 1 trong biển diễn nhị phân của <img src="https://tex.s2cms.ru/svg/n" alt="n" />.</br>
Từ đó ta suy ra ngay hệ quả sau: Nếu <img src="https://tex.s2cms.ru/svg/n" alt="n" /> là số nguyên dương có dạng <img src="https://tex.s2cms.ru/svg/2%5Ew%20-%201" alt="2^w - 1" />, khi đó tất cả các số trên hàng thứ <img src="https://tex.s2cms.ru/svg/n" alt="n" /> của tam giác Pascal đều là số lẻ.</br>
Vậy ta giải quyết trọn vẹn bài toán.</br>
