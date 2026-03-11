# Data-Mining
## Khai Phá Dữ Liệu Khách Hàng 
### 0. Người thực hiện
- Vũ Thị Kim Ngân
### 1. Thông Tin Về Dataset
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
## 3 Làm sạch dữ liệu:
- Trực quan tập dữ liệu và loại bỏ Outlier
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/1removeOutlier%20.png)
- Kiểm tra tìm Missing data và fill bằng phương pháp mean
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/2mean.png)

- Tạo các cột cần thiết và chuyển đôi kiểu dữ liệu
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/4calc.png)

- Vẽ biểu đồ tương quan
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/5chr.png)

# 4. Khai Phá Dữ Liệu Bằng Công Cụ SSAS:
`SSAS (SQL Server Analysis Services) là một công cụ phân tích dữ liệu của Microsoft SQL Server. Nó cho phép người dùng tạo các mô hình dữ liệu đa chiều (multidimensional) và mô hình dữ liệu phẳng (tabular) để phân tích dữ liệu từ các nguồn khác nhau`
## 4.1 Sử Dụng Thuật Toán Microsoft Clustering
`Microsoft Clustering là một phần của Microsoft SQL Server Analysis Services (SSAS) và được sử dụng để phân tích dữ liệu và phát hiện các mẫu trong dữ liệu. Microsoft Clustering là một thuật toán phân cụm (clustering algorithm) và có thể được sử dụng để phân loại các đối tượng dữ liệu vào các nhóm dựa trên các đặc tính chung của chúng`
- Thực hiện thuật toán để phân cụm dựa trên  tập thuộc tính: "Education","Children","Age","Income","Spent"
- Thực Hiện Tìm Số Cụm Phù Hợp Bằng Elbow
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/6elbow.png)
- Chọn các thuộc tính đầu vào và đầu ra
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/7inOut.png)
- Kết quả phân cụm dữ liệu sau khi Deloy
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/8deloy.png)
- Kết quả Cluster profiles
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/9clusterProf.png)
`Cột states là một cột được tạo ra bởi thuật toán clustering để đánh giá độ phân bố của các điểm dữ liệu trong các nhóm. 
Độ tuổi trung bình phân bổ ở 53,10 tuổi, người có độ tuổi cao nhất là 82, thấp nhất là 26 tuổi.
Thu nhập ở đây cao nhất là 116.207 đô la, thấp nhất là 1.730 đô, thu nhập trung bình của khách hàng là 51.968 đô la.
Các khách hàng có số trẻ con trong gia đình cao là là 3 người con, trung bình là 1 con, và không có đứa con nào trong gia đình.
Ở biến spent, cho ta thấy mức chi tiêu trung bình của khách hàng là 605 đô la, cao nhất là 2400 đô, thấp nhất là 5 đô la.`
- Đánh giá từng cụm 
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/10DG.png)
- Gán nhãn cụm khách hàng
-	Cluster 2: Khách hàng tốt. Đây là nhóm khách hàng có chi tiêu, thu nhập, tần suất mua hàng và sự hài lòng cao thứ hai. Họ là những khách hàng tiềm năng và có thể trở thành khách hàng ưu tú nếu được chăm sóc tốt
-	Cluster 1:  Khách hàng ưu tú. Đây là nhóm khách hàng có chi tiêu, thu nhập, tần suất mua hàng và sự hài lòng cao nhất. Họ là những khách hàng trung thành và quan trọng nhất của bạn
-	Cluster 4: Khách hàng kém. Đây là nhóm khách hàng có chi tiêu, lợi nhuận, tần suất mua hàng và sự hài lòng thấp nhất. Họ là những khách hàng không quan tâm hoặc không phù hợp với sản phẩm hoặc dịch vụ của bạn. Bạn cần xem xét lại chiến lược phục vụ hoặc từ bỏ họ để tập trung vào các nhóm khách hàng khác
-	Cluster 3: Khách hàng bình thường. Đây là nhóm khách hàng có doanh số, lợi nhuận, tần suất mua hàng và sự hài lòng ở mức trung bình. Họ là những khách hàng ổn định và cần được duy trì mối quan hệ
-	Cluster 5: Khách hàng có tiềm năng. Đây là nhóm khách hàng có doanh số, lợi nhuận, tần suất mua hàng thấp nhưng có sự hài lòng cao. Họ là những khách hàng có nhu cầu và mong muốn mua hàng của bạn nhưng chưa được kích hoạt hoặc thuyết phục đủ. Bạn cần tăng cường các chiến dịch marketing và bán hàng để chuyển đổi họ thành khách hàng tốt hoặc ưu tú
-	Cluster Characteristics
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/11ClusterChracter.png)
`Bảng này cho thấy các biến số quan trọng nhất để phân biệt các nhóm khách hàng trong tập dữ liệu. Các biến số này được sắp xếp theo thứ tự giảm dần của xác suất xuất hiện trong các nhóm khách hàng.`
- Cluster Discrimination
`Chuyển qua tab cluster Discrimination, ta có thể so sánh giữa 2 cụm:
Nếu bạn muốn tìm hiểu về nhóm khách hàng có chi tiêu cao nhất, bạn có thể so sánh cụm 2 và cụm 1, vì hai cụm này có giá trị Spent cao nhất.`
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/12clustermax.png)
-	Prediction
`Chuyển qua tab Mining Model Prediction, ta có thể dự đoán 1 người có các đặc tính như thế thì sẽ thuộc cụm nào. Ở dưới ta cần phân cụm 1 người có tuổi là 33, có số con là 2 , trình độ Education là Postgraduate, thu nhập đạt 22000 và chi tiêu khoảng 3000`
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/132000.png)
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/143000.png)
## 4.2 3.	Thuật toán Decision Tree
`Thuật toán Decision Tree là một thuật toán học máy (machine learning) được sử dụng để phân loại và dự đoán giá trị của các đối tượng dữ liệu dựa trên các đặc tính của chúng. Thuật toán này tạo ra một cây quyết định (decision tree) dựa trên các quyết định được đưa ra dựa trên các đặc tính của dữ liệu.
Sử dụng thuật toán decision tree để xây dựng các luật IF - THEN để dự đoán khả năng người đó có phản hồi lại chiến dịch tiếp thị mới nhất hay không.`
- Chọn key, input và biến dự đoán là respone
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/15response.png)

- Kết quả sau khi process model

![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/16afterproc.png)

`	Từ kết quả trên ta có thể gom lại được 1 số luật như sau:`
-	Đối với khách hàng phản hồi với chiến dịch tiếp thị (respone = 1)
-	Nếu khách hàng không chấp nhận tham gia chiến dịch tiếp thị 5 nhưng tham gia vào chiến dịch tiếp thị 3 thì khả năng người đó phản hồi lại chiến dịch tiếp thị mới nhất đạt gần 44%.
-	Đối với khách hàng không phản hồi với chiến dịch tiếp thị (respone = 0) 
-	Đối với khách hàng không chấp nhận tham gia chiến dịch tiếp thị 5 và chiến dịch tiếp thị 3 và số tiền bỏ ra mua thịt nhỏ hơn 520$ trong 2 năm thì khả năng người đó không phản hồi lại chiến dịch mới đạt khoảng 91,5%. 
-	Cũng tương tự khách hàng không chấp nhận tham gia chiến dịch tiếp thị 5 và chiến dịch tiếp thị 3 nhưng số tiền chi ra mua thịt lớn hơn 520$ trong 2 năm thì khả năng người đó không phản hồi lại chiến dịch đạt khoảng 70,5%.
- Trong số các biến dự đoán, ta thấy 3 biến Accepted Cmp3, Accepted Cmp5 và Meat quan trọng và ảnh hưởng nhất đến biến kết quả.
- 
![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/17accepted.png)

- Thực hiện đánh giá mô hình dựa vào confusion matrix

![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/18confusion.png)

Độ chính xác của mô hình đạt 88% .
- Preiction

![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/19preiction.png)

`Kết quả xác suất 52% người đó phản hồi lại chiến dịch tiếp thị mới nhất. Kết quả này đúng với dự đoán của nhóm. Vì ta thấy người này có chấp nhận tham gia cả 3 chiến dịch là 1,3,5 và số tiền chi ra mua thịt > 600$ nên khả năng cao lớn hơn 50% người đó phản hồi lại chiến dịch tiếp thị mới nhất.  

![image](https://raw.githubusercontent.com/kimngan919-tech/Data-Visualization/ede3dfb6cff5bf8e83d39d0bfa2aa52d4da9974a/Img/20e.png)
