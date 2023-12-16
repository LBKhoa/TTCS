# ĐỀ TÀI THỰC TẬP CƠ SỞ: GIẢI THUẬT TÌM ĐƯỜNG ĐI NGẮN NHẤT
## 1.Tổng quan.
### 1.1.Lý do chọn đề tài:
-Đường đi ngắn nhất là một vấn đề quan trọng trong nhiều lĩnh vực như giao thông, logistics và trí tuệ nhân tạo.  


-Nắm vững và so sánh 3 giải thuật Dijkstra, Floyd và Bellman trong bài toán tìm đường đi ngắn nhất.


-Hiểu rõ ý tưởng, cách hoạt động, độ phức tạp và ưu nhược điểm của từng giải thuật.
### 1.2 Mục tiêu nghiên cứu:
-Nắm vững kiến thức về các giải thuật tìm đường đi ngắn nhất.


-Áp dụng và thực hành triển khai các giải thuật, đồng thờ áp dụng các ngôn ngữ đã học C/C++/JS.


-Đề xuất cải tiến và tối ưu hóa giải thuật để tăng hiệu suất.


Điều kiện để tìm đường đi ngắn nhất từ đỉnh s -> t có lời giải:


### 1.Phải tồn tại đường đi từ s tới t:
	-Đồ thị vô hướng liên thông hoặc đồ thị có hướng liên thông mạnh.

 
	-Đồ thị vô hướng, trong đó s, t thuộc một thành phần liên thông.

 
	-Đồ thị có hướng có đường đi từ s tới t .
### 2.Đồ thị không chứa chu trình âm:
	-Đồ thị vô hướng không có cạnh âm.

 
	-Đồ thị có hướng không có chu trình âm.

 ## Ý tưởng:
 -Tại đỉnh cần xét, ta thử đường đi qua các đỉnh trung gian để đến đích.

 
-Cập nhật đường đi ngắn nhất nếu tìm được đường đi tốt hơn đường đi tốt nhất đã biết.


-Thông tin cần lưu:
+ Độ dài đường đi ngắn nhất từ 𝑠 → 𝑡 đã biết.

  
+ Đỉnh nằm trước v trên đường đi ngắn nhất đã biết.
## Thuật toán Dijkstra
-Cho đồ thị đơn vô hướng liên thông 𝐺 có trọng số dương. Tìm đường từ đỉnh 𝑠 đến 𝑡 của 𝐺 sao cho tổng trọng số của đường đi này là nhỏ nhất.


-Dijkstra-nhà khoa học máy tính người Hà Lan đã đề xuất thuật toán tìm đường đi ngắn nhất từ một đỉnh đến tất các các đỉnh còn lại trong đồ thị vô hướng có trọng số dương.

-Dijkstra là một thuật toán để tìm đường đi ngắn nhất từ một đỉnh đến các đỉnh còn lại.
### Ký hiệu:
-𝑑[𝑡] là nhãn của đỉnh 𝑡, độ dài ngắn nhất của đường đi từ 𝑠 đến 𝑡.


-𝑎[𝑠, 𝑡] trọng số cạnh/cung từ 𝑠 đến t.
### Theo như hình trên, nhãn của đỉnh 𝑣 là 𝑑[𝑣] sẽ được gán nhãn mới là:
                            𝑑[𝑣] := 𝑚𝑖𝑛(𝑑[𝑣], 𝑑[𝑢] + 𝑎[𝑢, 𝑣]) (1)

                            
-Nghĩa là, ở mỗi bước gán nhãn cho đỉnh, nếu nhãn mới lớn hơn hoặc bằng nhãn cũ thì giữa nguyên nhãn cũ, ngược lại thì thay nhãn cũ bằng nhãn mới.
### Mô tả thuật toán Dijkstra:
+	Khởi tạo nhãn cho các đỉnh theo quy tắc: đỉnh xuất phát 𝑠 được gắn nhãn bằng 0, các đỉnh kề với 𝑠 được gán bằng trọng số tương ứng, các đỉnh còn lại được gán nhãn là +∞.


+	Chọn đỉnh có nhãn nhỏ nhất (đỉnh này đã được cực tiểu hóa theo công thức 1) trong các đỉnh được gán nhãn ở bước đầu tiên, giả sử là đỉnh 𝑢.


+	Tiến hành gán lại nhãn và cực tiểu hóa nhãn cho các đỉnh còn lại theo 𝑢.


+	Thuật toán kết thúc khi tất các các đỉnh đã được chọn và đã được cực tiểu hoá nhãn.


=>	Đường đi ngắn nhất trong đồ thị là không duy nhất do nhiều đỉnh có thể có nhãn bé nhất bằng nhau.
### Đặc điểm thuật toán:
-Thuật toán Dijkstra sử dụng 𝑛 − 1 lần cực tiểu hóa nhãn.


-Mỗi lần cực tiểu hóa nhãn mất nhiều nhất 𝑛 phép toán so sánh nhãn.


-Độ phức tạp thời gian tính toán của thuật toán Dijkstra là 𝑂(𝑛^2).


-Thuật toán Dijkstra cũng có thể áp dụng cho đồ thị có hướng, chỉ cần lưu ý đến hướng của cung.

## Thuật toán Bellman-Ford
Cho một đồ thị có hướng hoặc vô hướng 𝐺, thuật toán Bellman-Ford tìm đường đi ngắn nhất từ một đỉnh xuất phát 𝑠 đến tất cả các đỉnh còn lại trong 𝐺, bao gồm cả cạnh có trọng số âm.
#### Ký Hiệu
+𝑑[𝑡]: Nhãn của đỉnh 𝑡, độ dài ngắn nhất của đường đi từ 𝑠 đến 𝑡.


+𝑎[𝑠, 𝑡]: Trọng số của cạnh/cung từ 𝑠 đến 𝑡.
### Mô tả thuật toán Bellman-Ford
##### 1.Khởi Tạo Mảng dist:
-Khởi tạo mảng dist với giá trị 0 cho đỉnh xuất phát và inf cho các đỉnh khác.
##### 2.Lặp V-1 Lần:
-Lặp qua tất cả các cạnh của đồ thị V-1 lần, với V là số đỉnh.


-Cập nhật giá trị dist nếu có đường đi ngắn hơn.
##### 3.Kiểm Tra Chu Trình Âm:
-Kiểm tra xem có chu trình âm hay không bằng cách lặp qua tất cả các cạnh và kiểm tra xem có cải thiện được giá trị dist nữa không.
##### 4.Hiển Thị Kết Quả:
-Kết quả là mảng dist, chứa độ dài ngắn nhất giữa đỉnh xuất phát và các đỉnh khác.
## Đặc Điểm Thuật Toán
+Chu Trình Âm: Có khả năng phát hiện và xử lý chu trình âm.


+Độ Phức Tạp Thời Gian: Độ phức tạp thời gian là O(V*E), với V là số đỉnh và E là số cạnh trong đồ thị.

## Thuật toán Floyd-Warshall
-Cho một đồ thị có hướng hoặc vô hướng 𝐺, thuật toán Floyd-Warshall tìm kiếm đường đi ngắn nhất giữa tất cả các cặp đỉnh trong 𝐺, có thể có cạnh có trọng số âm.
#### Ký Hiệu:
+dist[i][j]: Độ dài ngắn nhất của đường đi từ đỉnh i đến đỉnh j.


+V: Số đỉnh trong đồ thị.


+graph: Ma trận trọng số của đồ thị.
## Mô tả thuật toán
#### 1.Khởi Tạo Ma Trận dist:
+ Tạo ma trận dist ban đầu với dist[i][j] là độ dài ngắn nhất giữa đỉnh i và j.


+ d[i][i] được đặt là 0, và nếu không có cạnh nối trực tiếp từ i đến j, thì dist[i][j] được đặt là vô cùng.
#### 2.Cập Nhật Ma Trận dist:
+Duyệt qua mỗi đỉnh k trong đồ thị.


+Duyệt qua mỗi cặp đỉnh i và j.


+Nếu có đường đi từ i đến j thông qua đỉnh k ngắn hơn đường đi hiện tại, thì cập nhật dist[i][j].
#### 3.Hiển Thị Kết Quả:
+Kết quả là ma trận dist, chứa độ dài ngắn nhất giữa mọi cặp đỉnh.
## Đặc Điểm Thuật Toán
+Chu Trình Âm: Giữ tính chất không chu trình âm trong đồ thị.


+Độ Phức Tạp Thời Gian: Độ phức tạp thời gian là O(V^3), với V là số đỉnh trong đồ thị.
