Họ tên: Đồng Văn Hòa

MSSV: DTC235180213

### 4.1 Bảng So sánh

| Tiêu chí | Cách THỦ CÔNG (Traditional) | Cách DEVOPS (CI/CD Pipeline) |
|----------|---------------------------|------------------------------|
| **Làm sao để deploy?** | Lập trình viên tự sao chép file, tải mã nguồn lên máy chủ | Push code lên GitHub → pipeline tự chạy |
| **Mất bao lâu?** | 15phuts | ~10 giây |
| **Ai làm deploy?** | lập trình viên | GitHub Actions (máy tự làm) |
| **Có bị sai sót không?** | có thể sai sót | Không — pipeline nhất quán 100% |
| **Rollback nếu lỗi?** | Khôi phục bản sao lưu (backup) cũ hoặc sửa trực tiếp trên máy chủ bằng tay. | `git revert` + push → tự động rollback |
| **Làm sao biết deploy thành công?** | kiểm tra thủ công | GitHub Actions gửi notification ✅/❌ |
### 4.2 Sơ đồ DevOps Workflow
<img width="1266" height="561" alt="image" src="https://github.com/user-attachments/assets/37e4aafe-8262-4886-816e-217629204549" />

### 4.3 Trả lời Câu hỏi

1. **DevOps workflow tự động hóa những bước nào mà cách thủ công phải làm bằng tay?**
   
   → Build, test, deploy — tất cả đều được GitHub Actions làm tự động.

2. **Nếu bạn deploy sai (website bị lỗi), làm sao để quay lại phiên bản cũ?**
   
   → `git revert <commit>` hoặc `git reset --hard <commit>` rồi push → pipeline tự deploy bản cũ.

3. **GitHub Actions pipeline đã giúp bạn tiết kiệm bao nhiêu thời gian so với cách thủ công?**
   
   → Thủ công: download file → upload lên server → cấu hình → test (15-30 phút). DevOps: `git push` (10 giây).
