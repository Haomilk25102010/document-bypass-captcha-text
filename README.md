# Bypass Captcha chữ từ Hình ảnh 🛡️
#### Đây chỉ là tài liệu về cách bypass captcha hình ảnh
đây là 1 tài liệu nói về cách bypass captcha hình ảnh cho ae viết tool console thôi nhé, hiện tại tôi chỉ mò được cho ngôn ngữ php ae có thể áp dụng cho nó thành api.
### Step 1
- Câu lệnh chỉnh ảnh từ nhiễu sang bình thường ( trong các ngôn ngữ thì dùng thư viện os ) .
- ``` convert -colorspace gray -modulate 120 -contrast-stretch 10%x80% -modulate 140 -gaussian-blur 1 -contrast-stretch 5%x50% +repage -negate -gaussian-blur 4 -negate -modulate 130 original.jpeg clean.jpeg ```.
- Thay đường dẫn hình ảnh input và output nhé :D .
### Step 2
- Cái này khá là rối :D anh em làm theo nhé .
- Cài đặt thư viện chuyển hình ảnh sang văn bản .
- ``` composer require thiagoalessio/tesseract_ocr ```  💭 Cài đặt nó trong termux của bạn :D .
- Sau đó tạo file index.php để thực hiện nhé :D.
```ini
<?php 
requie "vendor/autoload.php"; 
use thiagoalessio\TesseractOCR\TesseractOCR;
echo (new TesseractOCR('clean.jpeg'))->whitelist(range(0, 9), range('A', 'Z'))->run();
```
- Rồi sau đó chạy file là được thôi, đây là cách bypass dành cho tool console anh em có thể cài argv cho đoạn code này để os file trong các ngôn ngữ khác nhé ( đoạn này không hiểu thì copy lên chatgpt kêu nó giải thích chứ tui lười ghi ra full ).
- Mod nó lại theo ý của bạn, đây chỉ là tài liệu với sự hỗ trợ của thư viện tesseractor mà tôi tìm hiểu được.
### Note
###### project này tạo ra với mục đích chia sẻ những gì tôi học được thôi nhé, không có mục đích cạnh tranh với ai , không phải captcha nào nó cũng giải được 
