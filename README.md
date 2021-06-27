# TL_Cau2_PTTKGT
## Áp dụng kỹ thuật Đệ quy quay lui để giải bài toán.
- Ký hiệu : 
  + w[i] là trọng lượng của gói hàng thứ i. (i = 1..n).
  + v[i] là giá trị của gói hàng thứ i. (i = 1..n).
- Mô hình bài toán có thể đưa về dạng bài toán quy hoạch tuyến tính nguyên tìm vectơ x = [ x1 , .. , xn ] ( với x1, .. , , xn là số lượng gói hàng 1,..,n được chọn ) như sau.
- Hàm mục tiêu : f = v1*x1 + ... + vn*xn >= max.
- Hệ ràng buộc :
  + w1*x1 + .. + wn*xn ≤ M
  + xi ≥ 0 ( i = 1 .. n )
- Để đánh giá giá trị của đồ vật so với trọng lượng ta dùng hệ số giá trị :
  + vi/wi ( i = 1..n).
- Ưu tiên các đồ vật có hệ số giá trị lớn chọn trước nên ta sắp xếp các gói hàng
từ cao đến thấp theo hệ số giá trị.
  + v1/w1 ≥ v2/w2 ≥ .. ≥ vn/wn.
- Dễ thấy giá trị tối đa của cái túi f(x) ≤ M*v1/w1.
- Vậy x1 có thể nhận các giá trị trong tập S1 = { k1 | k1 ≤ M/w1 }.
- Ứng với mỗi giá trị x1 = k1 <= S ta thiết lập một nhánh phương án có cập trên là:
  + k1*v1 + ( M – k1*w1 )* v2/w2.
- Và trong nhánh này, x2 có thể nhận các giá trị trong tập:
  + S2 = { k2 | k2*w2 ≤ ( M – k1*w1 ) }
- Ứng với mỗi giá trị x2 = k2 <= S2 ta lại thiết lập một nhánh phương án có cận trên
là : 
  + k1*v1 + k2*v2 + ( M – k1*w1 - k2*w2)* v3/w3.
- Tương tự quá trình thiết lập nhánh và cận trên cứ lặp lại cho tới khi nào không
thể chọn thêm một gói hàng nào nữa. (túi không thể chứa thêm gói hàng nào nữa).
- Để tìm phương án tối ưu ta đi theo nhánh có cận lớn nhất.
- Ký hiệu : a : giá trị đồ vật đang đạt được, b: cận trên của nhánh, M’ là trọng
lượng còn lại.

Chương trình (C):
Input : File balo.inp ( Đã xếp theo thứ tự nhỏ dần của v[i]/w[i].

4 8

5 3 2 4

10 5 3 6

Giải thích: File balo.inp tương ứng với:

n M

w[1] w[2] w[3] w[4]

v[1] v[2] v[3] v[4]

Ouput: File balo.out

15

1 1 0 0

Giải thích: File balo.out tương ứng với:

Vmax //Giá trị tối ưu.

x[1] x[2] x[3] x[4] //Số lượng loại đồ vật được chọn.
