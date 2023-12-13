
Bài toán Tìm Đường Đi Ngắn Nhất trên Đồ Thị Số
Điều Kiện để Tìm Đường Đi Ngắn Nhất từ 𝑠 → 𝑡 có Lời Giải
1. Phải Tồn Tại Đường Đi từ 𝑠 tới 𝑡:
Đồ thị vô hướng liên thông hoặc đồ thị có hướng liên thông mạnh.
Đồ thị vô hướng: 𝑠, 𝑡 thuộc một thành phần liên thông.
Đồ thị có hướng: Phải có đường đi từ 𝑠 tới 𝑡.
2. Đồ Thị Không Chứa Chu Trình Âm:
Đồ thị vô hướng không có cạnh âm.
Đồ thị có hướng: Không có chu trình âm.
Điều Kiện Liên Quan đến Đồ Thị:
- Liên Thông và Đồ Thị Mạnh Liên Thông:
Đồ thị phải là liên thông, tức là mọi đỉnh kết nối với nhau qua các cạnh.
Trong trường hợp đồ thị có hướng, đồ thị nên là mạnh liên thông, tức là có đường đi giữa mọi cặp đỉnh.
- Thành Phần Liên Thông:
Đối với đồ thị vô hướng, 𝑠 và 𝑡 phải thuộc cùng một thành phần liên thông để có đường đi giữa chúng.
3. Thông Tin Bổ Sung:
Trọng số cạnh và Hàm Trọng Số:
Đường đi ngắn nhất dựa trên trọng số của các cạnh, cần xác định trọng số này một cách chính xác.
Sử dụng hàm trọng số để mô tả cách tính tổng trọng số của đường đi.
Ý Tưởng:
Tại mỗi đỉnh cần xét, thử đường đi qua các đỉnh trung gian để đến đích.
Cập nhật đường đi ngắn nhất nếu tìm được đường đi tốt hơn đường đi tốt nhất đã biết.
Thuật Toán Dijkstra:
Cho đồ thị đơn vô hướng liên thông 𝐺 có trọng số dương.

Tìm đường từ 𝑠 đến 𝑡 sao cho tổng trọng số của đường đi là nhỏ nhất.

Ký Hiệu:

𝑑[𝑡]: Nhãn của đỉnh 𝑡, độ dài ngắn nhất từ 𝑠 đến 𝑡.
𝑎[𝑠, 𝑡]: Trọng số cạnh/cung từ 𝑠 đến 𝑡.
Thuật Toán:

Khởi tạo nhãn cho các đỉnh.
Chọn đỉnh có nhãn nhỏ nhất.
Gán lại nhãn và cực tiểu hóa nhãn cho các đỉnh còn lại.
Lặp lại bước 2 và 3 cho đến khi tất cả các đỉnh được chọn và nhãn đã được cực tiểu hóa.
Độ Phức Tạp Thời Gian:

𝑂(𝑛2)
Thuật Toán Floyd:
Tìm đường đi ngắn nhất giữa tất cả các cặp đỉnh trong một đồ thị có trọng số.

Có thể sử dụng để kiểm tra chu trình âm.

So Sánh với Dijkstra:

Dijkstra tìm đường đi từ một đỉnh đến các đỉnh còn lại.
Floyd tìm đường đi giữa tất cả các cặp đỉnh và có thể áp dụng cho đồ thị có hướng không chứa chu trình và trọng số cạnh có thể âm.
Độ Phức Tạp Thời Gian:

𝑂(𝑛3)
Thuật Toán:

Xét đồ thị vô hướng có trọng số 𝐺 = (𝑉, 𝐸), |𝑉 | = 𝑛 và 𝐴 = [𝑎𝑖𝑗 ], (𝑖, 𝑗 = 1, 𝑛).
Kết quả là hai ma trận 𝐷 và 𝑃.
Ví Dụ 2.2:
Tìm đường đi ngắn nhất từ 𝑠 đến các đỉnh còn lại của đồ thị.
Ví Dụ 2.3:
Xác định cây đường đi cho đồ thị có hướng 𝐺 với trọng số các cung.