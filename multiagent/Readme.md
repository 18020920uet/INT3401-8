# Bài tập số 2: Tìm kiếm có đối thủ

## Câu 1:

Hàm Reflex Agent xét đến các yếu tố:

Khoảng cách manhattan đến con ma gần mình nhất (x)
Số lượng thức ăn của trạng thái đó (y)
Khoảng thời gian con ma đang sợ mình (z)
Score sẽ xét đến các yếu tố sao cho con ma càng gần mình thì score càng thấp, nếu con ma đang sợ mình (y>0)), đồng thời số lượng thức ăn càng ít thì điểm càng cao. Sau khi chọn tham số, dùng công thức -(10/x + 50 _ z) nếu y = 0 và 50 _ z nếu y > 2 (2 được xem là khoảng cách an toàn đến ghost). Score cuối cùng được cộng với score của game khi đó (gameState.getScore())

## Câu 2:

sau khi gọi getAction thì xác định các state tiếp theo của pacman qua hàm maxVlue(), tính toán các bước đi và độ sâu sau đó lấy max của maximize mà min của minimize
Sau khi tính toán sẽ nhận được mảng gồm các actions và điểm cho action đó, dựa vào đó ta chọ action tốt nhất và trả về

## Câu 3

tương tự câu 2 nhưng áp dụng thuật toán alpha, beta để làm

## Câu 4

tương tự câu 3 nhưng thay vào đó ta lại tìm avg giá trị value trả về là tổng các giá trị của từng con ma nhân với xác suất của nó.

## Câu 5

Sau khi sử dụng bfs, gọi khoảng cách đến thức ăn ngắn nhất là x

Nếu số lượng thức ăn là 0, hàm trả về infinity (tốt nhất có thể)

Nếu pacman quá gần ghost trong khi scaredTime = 0, hàm sẽ trả về -infinity (trạng thái tệ, không được phép đến)

Ngược lại, score được tính theo công thức: gameState.getScore() _ 1000 + number_of_foods _ 100 + x \* 50 Hàm này ưu tiên việc lấy được nhiều điểm nhất, sau đó là giảm thiểu số lượng thức ăn, tiếp theo là giảm thiểu khoảng cách gần nhất đến một thức ăn.
