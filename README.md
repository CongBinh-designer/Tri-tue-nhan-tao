# Project Cá Nhân môn Trí Tuệ Nhân Tạo
- Đây là một dự án cá nhân của sinh viên Nguyễn Công Bình. Tổng quát về dự án là các thuật toán tìm kiếm và mô phỏng trong bài toán máy hút bụi.

## Giới thiệu về các thuật toán
**Nhóm thuật toán tìm kiếm mù thông tin (Uninformed Search)**
1. **Breatdh-First Search (BFS):** Gồm có 2 loại, mỗi loại sẽ có cách kiểm tra goal khác nhau. Sử dụng Queue (FIFO) để lưu trữ dữ liệu.
2. **Depth-First Search (DFS):** Gồm 2 loại kiểm tra goal như BFS. Sử dụng Stack (LIFO) để lưu trữ dữ liệu.
3. **Iterative Deepening Search (IDS):** Gồm 2 loại. Là thuật toán kết hợp giữa BFS và DFS với mỗi tầng độ sâu thuật toán sẽ tìm kiếm theo chiều rộng nhằm tiết kiệm không gian bộ nhớ.
4. **Uniform Cost Search (UCS):** Là thuật toán tìm kiếm theo chi phí, thuật toán được mở rộng theo đường đi có chi phí thấp nhất. Sử dụng Priority Queue lưu trữ dữ liệu.

**Nhóm thuật toán tìm kiếm có thông tin (Informed Search)**

1. **Greedy Best-First Search (GBFS):** Là thuật toán tìm kiếm tham lam, bằng việc sử dụng hàm (heuristic) để đánh giá chi phí, thuật toán sẽ ưu tiên chọn tuyến đường nhanh nhất nhưng không hẳn là tối ưu nhất.
2. **A\* Search:** Là thuật toán tìm kiếm thông minh bằng cách sử dụng hàm f(n) = g(n) + h(n) với g(n) để đánh giá chi phí và h(n) để đánh giá chi phí. Thuật toán sẽ tìm ra đường vừa ngắn và vừa tốn ít chi phi nhất.
3. **IDA\*:** Là thuật toán kết hợp giữa sự tối ưu của A* và sự tiết kiệm không gian bộ nhớ của DFS. Thuật toán sẽ tìm kiếm với độ sâu tăng dần theo các ngưỡng chi phí lấy từ hàm f(n).

**Nhóm thuật toán tìm kiếm cục bộ (Local Search)**
1. **Nhóm thuật toán leo đồi:** Gồm có bốn loại thuật toán leo đồi, thuật toán sẽ liên tục di chuyển tới các hàng xóm có giá trị mục tiêu tốt hơn tùy loại thuật toán sẽ có cách thức vận hành và chọn hàng xóm khác nhau.
   - Leo đồi đơn giản
   - Leo đồi dốc nhất
   - Leo đồi ngẫu nhiên
   - Leo đồi khởi động lại ngẫu nhiên
2. **Simulated Annealing:** Là một thuật toán tìm kiếm cục bộ lấy cảm hứng từ việc luyện kim. Thuật toán sẽ chấp nhận giá trị mục tiêu thấp hơn để thoát khỏi đỉnh cục bộ với khả năng chấp nhận giảm dần theo thời gian.
3. **Local Beam Search:** Là thuật toán tìm kiếm cục bộ được cải tiến từ thuật toán leo đồi. Thuật toán sẽ giữ lại k trạng thái tốt nhất và mở rộng đồng thời các trạng thái. Thuật toán sẽ giảm khả năng bị kẹt ở đỉnh cục bộ với việc khám phá nhiều hướng cùng lúc.

**Nhóm thuật toán tìm kiếm trong môi trường phức tạp (Complex Environment)**
1. **Sensorless Search:** Là thuật toán giải quyết bài toán bị "mù" hoàn toàn thông tin về vị trí. Thay vì tìm kiếm trên các trạng thái đơn lẻ, thuật toán thao tác trên các tập belief states, từ đó đưa ra một chuỗi hành động đảm bảo đến đích dù ban đầu đang đứng ở bất kỳ đâu.
2. **Partially Observable:** Là phương pháp khi tầm nhìn bị giới hạn. Dựa vào các thông tin thu thập được tại mỗi bước đi, thuật toán sẽ cập nhật vị trí hiện tại trong "đa vũ trụ" các khả năng để ra quyết định di chuyển tiếp theo một cách hợp lý nhất.
3. **And-Or Search:** Là thuật toán lập kế hoạch, nơi một hành động có thể dẫn đến nhiều kết quả khác nhau. Thuật toán sẽ lập ra một kế hoạch dự phòng dạng cây And-Or để đảm bảo Mario luôn có phương án xử lý mọi cạm bẫy có thể xảy ra.

**Nhóm thuật toán cho bài toán thỏa mãn ràng buộc**
1. **Backtracking Search:** Là một dạng tìm kiếm theo chiều sâu chuyên dụng cho CSP. Thuật toán sẽ thử gán màu cho từng ô bản đồ một, nếu phát hiện một ô vi phạm ràng buộc, nó sẽ quay lui bước trước đó để thử một màu khác.
2. **Forward Checking:** Là kỹ thuật tối ưu hóa kết hợp Backtracking. Mỗi khi tô một màu, thuật toán sẽ nhìn trước và loại bỏ màu đó khỏi danh sách các màu hợp lệ của các ô lân cận chưa tô. Giúp phát hiện sớm các ngõ cụt và giảm thiểu số lần quay lui.
3. **Min Conflicts:** Là thuật toán tìm kiếm cục bộ cho CSP. Thuật toán bắt đầu bằng cách gán màu ngẫu nhiên cho toàn bộ bản đồ. Sau đó ở mỗi bước, thuật toán sẽ chọn lại màu cho một ô đang bị vi phạm sao cho số lượng xung đột giảm xuống mức thấp nhất cho đến khi bài toán được giải.
4. **AC-3 (Arc Consistency):** Thay vì đi tìm lời giải ngay, thuật toán sẽ kiểm tra các cặp biến có ràng buộc với nhau và loại bỏ những giá trị chắc chắn không thể thỏa mãn ràng buộc đó. Trong quá trình này có biến nào bị xóa hết giá trị thì có thể kết luận ngay rằng bài toán vô nghiệm. AC-3 thường được dùng như một bước "dọn đường", giúp giảm số lượng trường hợp cần thử khi tìm kiếm lời giải.

### Công Nghệ Sử Dụng
**Ngôn ngữ lập trình:** Python
**Thư viện giao diện:** Tkinter
