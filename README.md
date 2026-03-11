 Đồ án tương tác trực quan hóa dữ liệu và áp dụng Machine Learning
---------------------------------------
# 1. Giới thiệu đề tài
- Nhận thấy Marketing là một lĩnh vực quan trọng trong kinh doanh và được áp dụng rộng rãi trong nhiều ngành công nghiệp. Dữ liệu về marketing cung cấp thông tin về xu hướng tiêu dùng, phản hồi khách hàng, chiến lược tiếp thị và quảng cáo, hiệu quả các chiến dịch tiếp thị, và nhiều yếu tố khác liên quan đến việc xây dựng và quản lý thương hiệu.
Sử dụng trực quan hóa dữ liệu trong marketing có nhiều lợi ích, bao gồm:
-	Hiểu rõ hơn về khách hàng: Khai phá dữ liệu giúp phân tích và hiểu rõ hơn về thông tin khách hàng, từ đó có thể tạo ra chiến lược marketing phù hợp và tăng cường sự tương tác với khách hàng.
- Tối ưu hóa chiến dịch quảng cáo: Bằng cách sử dụng khai phá dữ liệu, các nhà quảng cáo có thể tối ưu hóa chiến dịch quảng cáo của mình, từ việc chọn đối tượng khách hàng phù hợp cho đến tối ưu hóa chiến lược quảng cáo.
- Phân cụm khách hàng,từ đó hiểu rõ từng nhóm khách hàng và có chiến lược tối ưu cho từng nhóm khách hàng.
# 2.Thông tin về dataset
- Tập dữ liệu mà nhóm chúng em chọn có tên là "Marketing Data" và được lưu trữ trên trang Kaggle. Nguồn dữ liệu thu thập: https://www.kaggle.com/datasets/jackdaoud/marketing-data 
- Tập dữ liệu này bao gồm thông tin về các chiến dịch tiếp thị của một công ty trong vòng 3 năm (2012-2014). 
- Tập dữ liệu này bao gồm các biến : Đã có chi tiết trong file readme.txt
# 3. Nội dung chính dự án
## 3.1 Làm sạch dữ liệu:
- Trực quan tập dữ liệu và loại bỏ Outlier
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/95a75a95-88db-4203-822d-2eff18d63d59)

- Kiểm tra tìm Missing data và fill bằng phương pháp mean
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/ec0071fa-71ac-4f5f-a5dc-630bf23b874c)

- Tạo các cột cần thiết và chuyển đôi kiểu dữ liệu
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/90f7702a-07f0-4791-b546-86628926660b)

- Vẽ biểu đồ tương quan
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/2afa4274-7619-41af-9d88-b55c1a4cf5ca)

## 3.2 Tiền xử lí dữ liệu:
- Mã hóa các cột biến phân loại
- Chuẩn hóa dữ liệu bằng phương pháp Scale data using Standard Scaler
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/5b4b0f1d-848e-481e-affa-a857d33b55a4)

- Giảm chiều dữ liệu xuống còn 3 thuộc tính và trực quan các quan sát
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/f92b037f-0a24-433d-a9fc-692709f96559)

3.2 Xây dựng thuật toán K-means phân cụm khách hàng:
- Tìm số cụm K phù hợp bằng Elbow
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/428bdef6-bee0-482a-ac0d-8bb1ceb40df2)

- Tìm thuật toán phân cụm phù hợp
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/817968da-8ea9-4c9e-82db-5b9b20b31c50)

- Trực quan hóa kết quả phân cụm
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/98f2b9fd-375c-4989-9ea4-11128727b44d)

## 3.4 Đánh giá kết quả
- Sự phân bố các cụm
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/f661bbd2-0ac4-4909-8d8b-49552ecca130)

- Phân cụm dựa trên tổng chi tiêu và thu nhập
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/281039e4-2baa-49b9-897c-c43ffb5813e7)

##### Nhóm 0: chi tiêu thấp và thu nhập thấp
##### Nhóm 3: chi tiêu thấp và thu nhập trung bình
##### Nhóm 2: chi tiêu cao và thu nhập trung bình
##### Nhóm 1: chi tiêu cao và thu nhập cao
- Gán nhãn cụm dữ liệu
##### chúng ta sẽ phân loại Nhóm 0 là Khách hàng Bình thường, Nhóm 1 là Khách hàng Đặc biệt, Nhóm 2 là Khách hàng Tốt, và Nhóm 3 là Khách hàng có tiềm năng.
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/59fb6647-3f37-41ab-9b35-48b3d269169c)

- Chi tiêu của từng cụm khách hàng
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/a54c1d2b-93c8-448a-b64c-bcf528ae78b7)

- Mức chi tiêu cho từng mặt hàng của từng cụm khách hàng
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/a233adb7-f5c8-4bc8-be5a-78c6e79e4df5)

- Tỷ lệ chấp nhận chiến dịch quảng cáo của từng nhóm khác hàng
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/f15a93cf-bb54-4acb-85ff-3268652f60c1)

- Kết quả mua hàng qua khuyến mại
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/819d9250-a1a0-47ce-b88f-8e20c01057a3)

# 4 Dashboard trên PowerBI
![image](https://github.com/nguyenthanhhungDE/Data-Visualization/assets/134383281/f2165015-4e60-4010-bc4f-2d359dfd631b)


