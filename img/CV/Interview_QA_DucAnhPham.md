# 🎤 Interview Q&A — Duc Anh Pham
---

## 🏥 MediCare — Clinic Appointment System
*(Individual graduation project — Spring Boot, PostgreSQL, Docker)*

**Q: Bạn tự làm project này một mình không?**
> "Vâng, đây là đồ án tốt nghiệp cá nhân của em. Em tự thiết kế database schema, xây dựng REST API bằng Spring Boot 3, và tích hợp JWT authentication. Em cũng tự setup Docker để container hóa ứng dụng. Trong quá trình làm, em dùng AI (ChatGPT) để hiểu các khái niệm của Spring Boot như Dependency Injection, JPA relationships — em đọc giải thích của AI, sau đó tự coding lại và hiểu tại sao code chạy được."

**Q: Bạn đã xử lý authentication như thế nào?**
> "Em implement JWT token — user login thì server trả về token, client gửi token đó trong header cho các request tiếp theo. Em học cách làm từ documentation và nhờ AI giải thích flow, sau đó tự viết SecurityConfig và filter. Em hiểu được cơ bản là stateless authentication hoạt động thế nào, dù em biết trong thực tế còn nhiều edge case em chưa xử lý được."

**Q: Bạn học Spring Boot từ đâu?**
> "Em học qua kết hợp: đọc official docs, xem tutorial, và dùng AI để hỏi khi bị stuck. Khi không hiểu một concept, em hỏi AI giải thích rồi thử code theo — nếu vẫn lỗi thì hỏi tiếp tại sao lỗi. Em biết mình còn yếu về Spring Boot nhưng em đã hiểu được flow cơ bản và có thể làm việc được."

---

## 📰 Bina — University Magazine Portal
*(Team of 5 — primary developer — ASP.NET Core MVC, C#, Firebase)*

**Q: Team bạn làm như thế nào? Bạn đóng góp phần gì?**
> "Team em có 5 người, nhưng em là người code chính. Các bạn còn lại hỗ trợ phần UI, viết tài liệu và test. Em xây dựng đa số fontend và backend: role-based routing cho 5 roles, flow nộp bài của Student, flow review của Coordinator, và tích hợp Firebase Storage để upload file. Em cũng setup Google OAuth và Microsoft OAuth cho phần đăng nhập."

**Q: Tại sao chọn ASP.NET Core? Bạn biết C# từ trước chưa?**
> "Thật ra đây là lần đầu em làm project với C# và .NET. Em chọn vì muốn thử một tech stack khác với PHP và Java mà em đã làm trước đó. Em dùng AI để học C# syntax và hiểu Entity Framework Core — đặc biệt phần migration và relationship giữa các entities. Đây là project em học được nhiều nhất vì em phải tự đẩy mình ra khỏi comfort zone."

**Q: Làm nhóm 5 người có khó khăn gì không?**
> "Khó nhất là phân chia task rõ ràng và tránh conflict code trên Git. Em học cách dùng branch và pull request để merge code. Đôi khi có conflict thì em tự resolve vì em hiểu codebase nhất trong nhóm."

---

## 🛒 Flip-Mart — E-Commerce Website
*(Team of 2 — Laravel 9, Stripe)*

**Q: Bạn và teammate phân chia công việc thế nào?**
> "Em và bạn Vũ làm cùng nhau. Em chủ yếu phụ trách backend: thiết kế database MySQL, viết routes và controllers trong Laravel, xử lý logic giỏ hàng và tích hợp Stripe. Bạn Vũ hỗ trợ phần frontend với Blade templates và Tailwind CSS. Cả hai cùng review code và test trước khi merge."

**Q: Bạn tích hợp Stripe như thế nào?**
> "Em dùng Stripe PHP SDK. Em đọc documentation của Stripe và nhờ AI giải thích flow: tạo PaymentIntent ở server, gửi client secret về frontend, rồi frontend dùng Stripe.js để xử lý card. Em chưa xử lý được hết các edge case như refund hay webhook nhưng luồng thanh toán cơ bản chạy được."

**Q: Bạn có kinh nghiệm làm việc nhóm không?**
> "Có, em học được rằng communication quan trọng hơn code. Khi bị stuck hoặc thay đổi hướng, em báo với teammate ngay để tránh làm lại việc của nhau. Cả hai dùng GitHub để quản lý code và ClickUp để track task."

---

## 🧘 Yoga Class Management App (Android)
*(Individual coursework — Java, Firebase, Kotlin)*

**Q: Bạn chưa có kinh nghiệm Android, bạn học thế nào?**
> "Đây là lần đầu em làm Android app. Em bắt đầu bằng cách đọc Android Developer docs, xem các tutorial cơ bản về Activity và Intent. Khi gặp vấn đề về lifecycle hoặc Firebase SDK, em nhờ AI giải thích và thử code theo. Em không dám nói mình giỏi Android, nhưng em đã hoàn thành được app với đầy đủ CRUD và Firebase integration."

**Q: Tại sao dùng cả SQLite lẫn Firebase?**
> "Em dùng Firebase Firestore để sync data lên cloud và SQLite để lưu local — ý tưởng là app vẫn có data khi offline. Thật ra phần sync giữa hai cái này em chưa làm được hoàn toàn mượt mà, nhưng em hiểu được concept và tại sao cần cả hai."

---

## 📊 House Price Prediction — Data Analysis
*(Individual — Python, scikit-learn, XGBoost, Tableau)*

**Q: Bạn có background về Data Science không?**
> "Không nhiều — đây là project em thử vì tò mò. Em học Python data science qua tutorial và nhờ AI giải thích các khái niệm như correlation, regression, feature importance. Em hiểu được flow cơ bản của một data project: clean data → EDA → build model → visualize. Em không tự tin về mặt toán học phía sau, nhưng em biết cách chạy và đọc kết quả."

**Q: Model của bạn có accuracy tốt không?**
> "Em chưa tối ưu nhiều — em tập trung vào việc hiểu pipeline hơn là đạt accuracy cao. XGBoost cho kết quả tốt hơn linear regression, và em dùng feature importance để xem sqft_living và location ảnh hưởng nhiều nhất đến giá. Nếu có thêm thời gian em muốn thử hyperparameter tuning."

---

## 🎵 Tune Source System — Music CD Store
*(Individual — PHP, MySQL)*

**Q: Project này khác gì so với Flip-Mart?**
> "Tune Source là project em làm trước, dùng plain PHP (PDO) không có framework — em phải tự viết tất cả từ routing đến query. Flip-Mart sau đó dùng Laravel nên có nhiều thứ được tự động hóa hơn. Làm Tune Source giúp em hiểu bên dưới Laravel làm gì, như connect database, sanitize input, quản lý session."

---

## 💡 Câu hỏi chung thường gặp

**Q: Bạn dùng AI để code — vậy bạn thật sự hiểu code đó không?**
> "Em dùng AI như một người thầy giải thích, không phải để copy-paste mù quáng. Workflow của em là: gặp vấn đề → hỏi AI giải thích concept → tự viết lại code → nếu lỗi thì hỏi tại sao lỗi. Em không dám nói hiểu 100%, nhưng em có thể giải thích được logic chính của từng phần em viết. Và em biết điểm yếu của mình — đó là lý do em apply intern để được học từ các senior developer thật sự."

**Q: Bạn thấy mình mạnh nhất ở tech stack nào?**
> "Em tự tin nhất với PHP/Laravel và Java/Spring Boot vì em đã làm nhiều project nhất với hai stack này. C# và Python em chỉ mới bắt đầu qua project gần đây. Quan trọng hơn stack cụ thể, em nghĩ mình mạnh ở việc đọc hiểu code, debug theo từng bước, và học nhanh khi có hướng dẫn."

**Q: Tại sao bạn muốn làm intern ở đây?**
> "Em muốn được làm việc trong môi trường chuyên nghiệp để thấy sự khác biệt giữa code trong trường và code thật sự. Em muốn học cách viết code sạch hơn, làm việc nhóm theo chuẩn, và được review bởi người có kinh nghiệm. Em biết mình còn nhiều thiếu sót nhưng em sẵn sàng học và không ngại làm từ những việc nhỏ nhất."

---
