#Bank Term Deposit Prediction
##Mục tiêu dự án
Xây dựng mô hình dự đoán khả năng khách hàng sẽ đăng ký sản phẩm tiền gửi có kỳ hạn dựa trên thông tin cá nhân và lịch sử tương tác với ngân hàng. Dữ liệu có sự mất cân bằng giữa hai lớp (khách hàng đăng ký và không đăng ký), nên cần xử lý cẩn thận bằng các kỹ thuật như SMOTE.

##Thông tin dữ liệu
Dữ liệu bao gồm thông tin từ các chiến dịch tiếp thị của ngân hàng, chia thành 4 nhóm chính:

###Bank Client Data
age: Tuổi
job: Nghề nghiệp
marital: Tình trạng hôn nhân
education: Trình độ học vấn
default: Có nợ tín dụng không?
balance: Số dư tài khoản trung bình (€/năm)
housing: Có vay mua nhà?
loan: Có vay cá nhân?

###Last Contact Info
contact: Phương thức liên hệ ("cellular", "telephone", "unknown")
day: Ngày liên hệ
month: Tháng liên hệ
duration: Thời lượng cuộc gọi (giây)

###Campaign Performance
campaign: Số lần liên hệ trong chiến dịch hiện tại
pdays: Số ngày từ lần liên hệ trước đó (-1 nếu chưa liên hệ)
previous: Số lần liên hệ trong các chiến dịch trước
poutcome: Kết quả của chiến dịch trước đó

###Output Variable
y: Khách hàng có đăng ký tiền gửi không? (1 = Yes, 0 = No)

##Quy trình thực hiện
###Tiền xử lý
Xử lý trùng lặp và giá trị thiếu
Loại bỏ các hàng có unknown trong job và education
Chuyển đổi biến phân loại sang dạng số

###EDA (Phân tích khám phá dữ liệu)
Phân tích mối quan hệ giữa các đặc trưng và biến mục tiêu (y)
Phát hiện mất cân bằng dữ liệu (class imbalance)
Đánh giá ảnh hưởng của từng biến bằng biểu đồ
Feature Engineering
Mapping biến phân loại sang số
Chuẩn hóa dữ liệu
Vẽ ma trận tương quan
Xây dựng mô hình

###So sánh 3 mô hình:
Logistic Regression
Random Forest Classifier
XGBoost Classifier
Huấn luyện mô hình trên dữ liệu gốc và dữ liệu đã cân bằng bằng SMOTE
Đánh giá mô hình
Sử dụng các metric: accuracy, precision, recall, f1-score
Đặc biệt chú ý đến lớp 1 (khách hàng đăng ký), vì đây là nhóm mục tiêu
