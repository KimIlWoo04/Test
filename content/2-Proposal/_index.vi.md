---
title: "Bản đề xuất"
date: "2025-11-25"
weight: 2
chapter: false
pre: " <b> 2. </b> "
---



# GENERATIVE AI TRAVEL PLANNER  
## Nền Tảng Lịch Trình Trò Chuyện Sử Dụng Kiến Trúc Serverless và Mô Hình Nền Tảng  

### 1. Tóm tắt điều hành  
Trình Lập Kế Hoạch Du Lịch bằng AI Sáng Tạo là một ứng dụng web không máy chủ, được thiết kế để giúp khách du lịch, các đại lý du lịch và chuyên gia trong ngành du lịch tạo ra các lịch trình cá nhân hóa một cách hiệu quả. Chỉ bằng cách nhập điểm đến, thời lượng chuyến đi và sở thích, người dùng sẽ nhận được kế hoạch chi tiết cho từng ngày do AI tạo ra, bao gồm các hoạt động, khung giờ và mô tả được điều chỉnh theo sở thích cá nhân. Nền tảng này được xây dựng trên các dịch vụ của AWS như AWS Lambda và Bedrock nhằm nâng cao trải nghiệm người dùng trong các ứng dụng thực tế, với tiềm năng ứng dụng rộng rãi trong các doanh nghiệp du lịch, startup du lịch và việc lập kế hoạch chuyến đi cá nhân. 

### 2. Tuyên bố vấn đề  
### Vấn Đề  
Việc lập kế hoạch cho một chuyến đi kéo dài nhiều ngày đòi hỏi một khoảng thời gian và công sức đáng kể để nghiên cứu điểm đến, sắp xếp các hoạt động và tạo ra một lịch trình mạch lạc. Du khách thường phải dành hàng giờ đồng hồ để xem qua nhiều website, blog và đánh giá khác nhau để ghép nối thành một kế hoạch chi tiết cho từng ngày, làm sao để phù hợp với sở thích và thời gian họ có. Các đại lý du lịch và chuyên gia trong ngành du lịch cũng phải đối mặt với những thách thức tương tự khi tạo ra các lịch trình tùy chỉnh cho khách hàng, dẫn đến những công việc thủ công lặp đi lặp lại. Do đó, tồn tại một nhu cầu cấp thiết về một giải pháp thông minh, tự động hóa, có khả năng tạo ra các kế hoạch du lịch cá nhân hóa một cách nhanh chóng, nhưng vẫn đảm bảo được chất lượng và sự phù hợp với sở thích của người dùng. 

### Giải Pháp và Lợi Ích  
Nền tảng này tận dụng AWS Amplify để cung cấp một ứng dụng web hoàn toàn không máy chủ với khả năng triển khai liên tục. Các yêu cầu của người dùng được xử lý thông qua một API GraphQL được xây dựng bằng AWS AppSync, giao tiếp với các hàm AWS Lambda để xử lý logic phía backend. Amazon Bedrock cùng với mô hình nền tảng Claude Haiku tạo ra các lịch trình thông minh, có ngữ cảnh dựa trên đầu vào của người dùng. Amplify Auth quản lý xác thực người dùng và kiểm soát quyền truy cập an toàn vào ứng dụng. Giải pháp cung cấp một giao diện đơn giản dựa trên HTML, nơi người dùng nhập điểm đến, thời lượng chuyến đi và sở thích, sau đó nhận được các lịch trình chi tiết từng ngày toàn diện, bao gồm hoạt động, khung thời gian và mô tả.

Các lợi ích chính bao gồm khả năng tạo lịch trình nhanh chóng, tiết kiệm hàng giờ nghiên cứu thủ công; các đề xuất được cá nhân hóa theo sở thích riêng biệt; và một kiến trúc có khả năng mở rộng để xử lý nhiều người dùng đồng thời. Phương pháp không máy chủ đảm bảo hiệu quả chi phí thông qua hình thức giá trả-theo-lượng-dùng, đồng thời minh chứng cho sự tích hợp thực tế giữa AI sáng tạo và các dịch vụ AWS hiện đại. Nền tảng này có thể được mở rộng cho các đại lý du lịch, doanh nghiệp du lịch hoặc các ứng dụng lập kế hoạch chuyến đi cá nhân.

### 3. Kiến trúc giải pháp  
Nền tảng vận hành dựa trên một kiến trúc AWS không máy chủ để cung cấp hệ thống tạo lịch trình du lịch được vận hành bởi AI. Các yêu cầu từ người dùng được tiếp nhận thông qua giao diện web được lưu trữ trên AWS Amplify, sau đó đầu vào được xử lý qua API GraphQL được quản lý bởi AWS AppSync. Logic phía backend sẽ do các hàm AWS Lambda đảm nhiệm, các hàm này tương tác với Amazon Bedrock để tạo ra các lịch trình cá nhân hóa bằng cách sử dụng mô hình nền tảng Claude Haiku. Việc xác thực người dùng và kiểm soát truy cập được quản lý thông qua Amplify Auth với sự tích hợp của Amazon Cognito. Kiến trúc chi tiết được mô tả bên dưới:

![GenAI Travel Planner Architecture](/images/Project_Architecture.drawio.png)

### Dịch vụ AWS sử dụng  
- **AWS Amplify**: Lưu trữ giao diện web dựa trên HTML với khả năng triển khai liên tục.
- **AWS AppSync**: Quản lý API GraphQL để xử lý dữ liệu hiệu quả và thiết lập kết nối thời gian thực giữa frontend và backend.
- **AWS Lambda**: Thực thi logic xử lý backend và xử lý các yêu cầu tạo lịch trình bằng AI.
- **Amazon Bedrock**: Cung cấp quyền truy cập vào mô hình nền tảng Claude Haiku để tạo ra các lịch trình thông minh.
- **Amazon Cognito (thông qua Amplify Auth)**: Quản lý việc xác thực người dùng và bảo mật quyền truy cập ứng dụng.  

### Thiết kế thành phần  
- **Giao diện Web**: AWS Amplify lưu trữ giao diện người dùng dựa trên HTML, nơi người dùng nhập thông tin điểm đến, thời lượng chuyến đi và sở thích, sau đó xem các lịch trình đã được tạo.
- **Tầng API**: AWS AppSync cung cấp một API GraphQL đảm nhiệm việc kết nối thông tin giữa giao diện người dùng và các dịch vụ backend.
- **Xử lý Backend**: Các hàm AWS Lambda đảm nhận logic nghiệp vụ, xử lý yêu cầu từ người dùng và điều phối các tương tác với các dịch vụ AWS khác.
- **Tạo lập bằng AI**: Amazon Bedrock cùng với mô hình nền tảng Claude Haiku tạo ra các lịch trình du lịch được cá nhân hóa, có tính đến ngữ cảnh dựa trên đầu vào của người dùng.
- **Quản lý Người dùng**: Amplify Auth tích hợp Amazon Cognito quản lý việc đăng ký, xác thực người dùng và đảm bảo quyền truy cập an toàn vào ứng dụng.

### 4. Triển khai kỹ thuật  
- **Ứng dụng Frontend**: Giao diện người dùng dựa trên HTML tích hợp biểu mẫu nhập liệu cho điểm đến, số ngày và sở thích. Giao diện hiển thị các lịch trình được AI tạo ra dưới dạng cấu trúc có phân tích chi tiết theo từng ngày, bao gồm hoạt động, khung giờ và mô tả.
- **Dịch vụ Backend**: Các hàm AWS Lambda xử lý yêu cầu API, tiếp nhận dữ liệu người dùng và tương tác với Amazon Bedrock. Yêu cầu hiểu biết về AWS SDK để gọi các mô hình nền tảng Bedrock và xây dựng prompt cho mô hình Claude Haiku.
- **Quản lý API và Dữ liệu**: Cấu hình AWS AppSync để định nghĩa lược đồ GraphQL API, bộ phân giải và nguồn dữ liệu. Yêu cầu hiểu biết về các thao tác GraphQL để kết nối yêu cầu frontend với các hàm backend.
- **Xác thực**: Thiết lập Amplify Auth với Amazon Cognito cho xác thực người dùng, hỗ trợ đăng ký bảo mật, đăng nhập và quản lý phiên làm việc với các endpoint API được bảo vệ.
- **Tích hợp AI**: Hiểu biết thực tế về Amazon Bedrock API để gọi mô hình, kỹ thuật tạo prompt cho việc xây dựng lịch trình du lịch và xử lý phản hồi. Nắm được các khả năng và giới hạn của mô hình Claude Haiku.
- **Triển khai**: Cấu hình AWS Amplify cho triển khai liên tục, quản lý môi trường và lưu trữ ứng dụng web. 

### 5. Lộ trình & Mốc triển khai  
- Tháng 1: Nghiên cứu các khái niệm và dịch vụ nền tảng của AWS
- Tháng 2: Lên kế hoạch và thiết kế kiến trúc dự án
- Tháng 3: Phát triển, kiểm thử và triển khai
    - Tuần 1: Thiết lập và cấu hình các dịch vụ AWS
    - Tuần 2: Phát triển backend và tích hợp Bedrock
    - Tuần 3: Phát triển frontend và kết nối API
    - Tuần 4: Kiểm thử, gỡ lỗi và triển khai 
 

### 6. Ước tính ngân sách  
<!-- Có thể xem chi phí trên [AWS Pricing Calculator](https://calculator.aws/#/estimate?id=621f38b12a1ef026842ba2ddfe46ff936ed4ab01)  
Hoặc tải [tệp ước tính ngân sách](../attachments/budget_estimation.pdf).  -->

### Chi phí hạ tầng  
- Amazon Bedrock: 2.10$/tháng
- AWS Lambda: 0$/tháng
- AWS Amplify: 0.27$/tháng
- AWS AppSync: 0.11$/tháng
- Amazon Cognito: 0.25$/tháng

Tổng cộng: 2.73$/tháng | 32.76$/năm 


### 7. Đánh giá rủi ro  
Rủi Ro  
- Nguy cơ giới hạn hạn ngạch dịch vụ hoặc vấn đề về tính khả dụng của Amazon Bedrock tại khu vực Singapore.
- Khả năng chạm ngưỡng giới hạn số lần gọi dịch vụ Bedrock hoặc Lambda trong quá trình kiểm thử.
- Chất lượng lịch trình không ổn định do phản hồi từ mô hình AI.  

Biện Pháp Giảm Thiểu  
- Theo dõi sát sao bảng thông tin tình trạng dịch vụ.
- Triển khai cơ chế kiểm tra tính hợp lệ của prompt (đầu vào) và lọc phản hồi từ AI.

Kế Hoạch Dự Phòng 
- Chuyển sang sử dụng các khu vực hoặc mô hình AWS thay thế nếu dịch vụ chính gặp hạn chế.
- Tạo sẵn các lịch trình dự phòng dựa trên mẫu có sẵn.  

### 8. Kết quả kỳ vọng  
- Ứng dụng không máy chủ hoạt động đầy đủ chức năng được triển khai trên AWS.
- Tích hợp liền mạch giữa các dịch vụ Amplify, AppSync, Lambda và Bedrock.
- Kỹ thuật tạo prompt (đầu vào) hiệu quả cho việc tạo lịch trình du lịch.
- Lượng token được tối ưu hóa, duy trì chi phí dưới 3 USD/tháng.
- Phản hồi từ mô hình ổn định và có định dạng thống nhất.
