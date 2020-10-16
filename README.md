Nguyễn Tú Anh - 18020146

MÔ TẢ CÁCH LÀM

câu 1:
Reflex Agent
Dùng khoảng cách mahattan đến vị trí thức ăn làm thông số để đánh giá. 
Tính toán từng khoảng cách đến thức ăn và lấy kết quả nhỏ nhất.
Trả về phủ định của kết quả để phản ảnh tỷ lệ nghịch của khoảng cách pacman đến 
thức ăn và điểm số. Duyệt qua tất cả thức ăn để thực hiện. Nếu có ma ở vị trí 
hiện tại và đang không trong scared time thì trả về số âm vô cùng. Nếu hành động
bị dừng lại thì cũng trả về số âm vô cùng. 

câu 2:
Minimax
Class Minimax với hàm getAction trả về hành động tốt nhất để di chuyển
ta triển khai 2 hàm là 
getMaxValue và getMinValue theo thuật toán minimax , đối với người chơi, điểm số trả
về giá trị lớn nhất trong các trạng thái kế nhiệm, đối với con ma, điểm số trả về giá
trị nhỏ nhất trong các trạng thái kế nhiệm. 
- getMaxValue:
tác tử hiện tại có chỉ số = 0 (người chơi : player)
lấy LegalActions của tác tử hiện tại để duyệt
check nếu không có hành động hoặc game win hoặc độ sâu vượt qua độ sâu mặc định
trả về giá trị state và stop
tiếp theo duyệt các trạng thái tiếp theo được generate , giá trị của các trạng thái 
hiện tại = getMinValue của các từng thái con và tăng chỉ số của argent lên 1 đơn vị để
duyệt tới tác tử tiếp theo (những con ma )
 và ta lấy giá trị lớn nhất cùng hành động ứng vs giá trị đó
- getMinValue:
tác tử hiện tại có chỉ số khác 0 (con ma)
Hoàn toàn ngược lại nhưng check chỉ số tác tử nếu đã duyệt hết các tác tử 1 lượt
trả chỉ số tác tử về 0 và tăng depth lên 1 đơn vị => quay lại getMaxValue 
nếu chưa thì tiếp tục đệ quy getMinValue qua hết lượt các con ma

câu 3:
Alpha-Beta
tương tự bài 2 nhưng áp dụng thêm cắt tỉa alpha-beta loại bỏ những lần duyệt không cần thiết
áp dụng hàm trên courses

câu 4:
Expectimax
tương tự bài 2 , nhưng khác ở getMinValue
thay vì trả về giá trị min ( tối ưu cho mỗi con ma ) ta sẽ dùng trung bình của tất cả giá
trị trạng thái tiếp theo của mỗi con ma và trả về giá trị đó. Tạo ra xác suất ngẫu nhiên hơn
cho việc di chuyển của con ma

câu 5:
Evaluation Function
dùng khoảng cách đến mỗi con ma , khoảng cách đến mỗi vị trí thức ăn và thời gian ma hoảng
sợ để tính toán lấy kết quả bài toán.
cách làm là :
duyệt qua tất cả các con ma : khi có con ma nào đang trong thời gian hoảng sợ thì điểm số
vẫn giữ nguyên , để cho pacman di chuyển như bình thường. Còn nếu con ma không còn thời
gian hoảng sợ nữa , điểm số sẽ cộng thêm khoảng cách nhỏ nhất đến con ma và trừ đi khoảng cách 
nhỏ nhất đến thức ăn. Như vậy pacman có thể ưu tiên đi đến thức ăn gần nhất và tránh xa con ma
gần nhất
trả về điểm số sau khi tính toán

