# BERT_For_Sentiment_Analysis

## Tổng quan về `Transformer`
- Giới thiệu
- Các thành phần chính của Transformer:
  - Cơ chế `Self - Attention`.
  - Cấu trúc `Encoder - Decoder`.
- Ứng dụng

## Bài toán Và mô hình sử dụng
- Bài toán:
  - Bài toán trong lĩnh vực Xử lý Ngôn ngữ Tự nhiên: Phân tích quan điểm (Sentiment analysis).
  - Bài toán được sử dụng để phân tích và nhận biết cảm xúc, ý kiến hoặc thái độ của một đoạn văn bản.
- Mô hình:
  - BERT (Bidirectional Encoder Representations from Transformers) là một mô hình ngôn ngữ tự nhiên dựa trên kiến trúc Transformer, có khả năng học biểu diễn từ hai phía và đã đạt được thành công đáng kể trong nhiều nhiệm vụ NLP.
  - Kiến trúc:
      - BERT bao gồm một số lớp mã hóa (encoder layers) dựa trên kiến trúc Transformer. Mỗi lớp mã hóa chứa các cơ chế tự chú ý và mạng nơ-ron truyền thẳng (feed-forward neural network).
      - Một trong những đặc điểm quan trọng của BERT là sử dụng mã hóa từ (word embeddings) để biểu diễn từng từ đầu vào và một mã hóa đoạn (segment embeddings) để phân biệt giữa các đoạn văn trong câu.
  - Huấn luyện: BERT được huấn luyện theo hai giai đoạn: Pre-training và Fine-tuning:
      - Trong giai đoạn Pre-training, mô hình được huấn luyện không giám sát trên một tác vụ dự đoán từ điền (masked language model) và một tác vụ dự đoán câu tiếp theo (next sentence prediction) trên dữ liệu lớn.
      - Sau khi hoàn thành giai đoạn Pre-training, BERT được Fine-tuning trên các tác vụ cụ thể, như phân loại văn bản hoặc trích xuất thông tin, bằng cách đào tạo thêm một số lớp phân loại trên đầu mô hình.

## Áp dụng vào tập dữ liệu `IMDB Dataset`
- Ta huấn luyện mô hình dựa trên tập dữ liệu `IMDB Dataset` gồm 25000 dòng và 2 cột thuộc tính: review và sentiment.
- Kết quả độ đo:
  | Metric          | Score      |
  |-----------------|------------|
  | Accuracy        | 0.8797     |
  | Precision       | 0.8716     |
  | Recall          | 0.8902     |
  | F1 Score        | 0.8808     |
- Nhận xét:
  - Accuracy: Độ chính xác tổng thể của mô hình là 0.88, tức là mô hình đúng khoảng 88% trong việc dự đoán đúng nhãn của dữ liệu.
  - Precision và Recall: Precision và recall đều cao cho cả hai nhóm nhãn, tương ứng là 0 và 1, với giá trị precision và recall đều trên 0.87. Điều này cho thấy mô hình có khả năng dự đoán chính xác cả hai nhãn và có tỷ lệ false positive và false negative thấp.
  - F1-score: F1-score, một trung bình điều hòa giữa precision và recall, là 0.88 cho cả hai nhóm nhãn. Điều này cho thấy mô hình có hiệu suất tốt trong việc cân bằng giữa precision và recall.

## Xây dựng giao diện web đơn giản
- Ta xây dựng bằng thư viện Flask, sử dụng HTML và CSS.
- Sau khi chạy trang web, ta nhấn vào `Click here` phía dưới:
  ![](https://drive.google.com/uc?export=view&id=1eVoj-Gj0knvINjzw8YDMRcdZn9k5sOQk)
  
- Ta sẽ đi tới trang web:
  ![](https://drive.google.com/uc?export=view&id=1ePaw1n5llz0R43zmq0-tfQ7oPUBkzRhd)
  
- Ta ví dụ bằng dự đoán nhận xét sau: `“This movie was a complete disappointment. The plot was confusing, the acting was terrible, and the dialogue felt forced. I couldn't connect with any of the characters, and the pacing was incredibly slow.”`
  ![](https://drive.google.com/uc?export=view&id=1WK2kjkvQ9hp-IZMUdX_ZVDGmNp93oPiM)
  
- Kết quả dự đoán đây là nhận xét tiêu cực và có tỉ lệ là 99.99%. Khi đọc nhận xét, ta có thể thấy ý nghĩa của câu đúng là tiêu cực, chứng tỏ kết quả dự đoán là đúng.

