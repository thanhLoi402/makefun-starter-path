# MakeFun Starter Path

[![make.fun · bring-the-humans-02](https://make.fun/badge/bring-the-humans-02.svg)](https://make.fun/bounty/bring-the-humans-02)
[![rank](https://make.fun/badge/bring-the-humans-02/thanhLoi402/makefun-starter-path/rank.svg)](https://make.fun/bounty/bring-the-humans-02/leaderboard)
[![reward](https://make.fun/badge/bring-the-humans-02/thanhLoi402/makefun-starter-path/reward.svg)](https://make.fun/bounty/bring-the-humans-02)

Từ brief đến bài dự thi đầu tiên với coding agent. Trong lượt đọc đầu, bạn có thể chọn một bounty hợp với kỹ năng và thời gian của mình, chuẩn bị môi trường rồi giao cho agent một việc có tiêu chí nghiệm thu.

**Công bố liên kết giới thiệu.** Chủ repo có thể được ghi nhận quyền lợi theo chương trình khi MakeFun xác minh lượt giới thiệu. Giải cuộc thi phụ thuộc vào kết quả và điều kiện từng bounty. [Mở qua mã thdrwbrr](https://make.fun/r/thdrwbrr) · [Mở make.fun trực tiếp](https://make.fun/)

## 1. Chọn việc bạn làm được từ đầu đến cuối

make.fun tổ chức các cuộc thi có brief, yêu cầu nộp và cách xếp hạng công bố riêng. Một bài có thể là hướng dẫn GitHub, một sản phẩm chạy được hoặc một chương trình có bộ chấm. Mở trang bounty đang nhận bài, tìm giờ đóng cổng và xem các điều kiện bắt buộc trước khi tạo repo hoặc bắt đầu phiên agent.

- **Nội dung và hình ảnh.** Chọn đề hướng dẫn hoặc trang giới thiệu nếu bạn có thể giải thích quy trình và kiểm tra sản phẩm khi người khác mở link. Dành thời gian cho ảnh thật và bằng chứng nếu brief yêu cầu.
- **Frontend và game.** Chọn đề có runtime bạn đã biết. Kiểm tra khả năng build, cách người chấm mở sản phẩm và các giới hạn về dịch vụ bên ngoài. Nếu cần host demo, tính cả thời gian publish và thử lại trong cửa sổ riêng tư.
- **Hệ thống và thuật toán.** Chọn đề có hợp đồng đầu vào, đầu ra và metric rõ ràng. Ưu tiên chạy được baseline với bộ dữ liệu hoặc harness dành cho development trước khi tối ưu.

## 2. Đọc kit theo thứ tự

1. Trên trang bounty, mở **Requirements** hoặc API requirements. Đọc điều kiện tham gia, sản phẩm bắt buộc, quy định repo và cách tính điểm. Ghi giờ UTC và giờ địa phương vào lịch.
2. Tải kit của đúng bounty. Mở `RULES.txt` lấy yêu cầu và ví dụ, rồi đối chiếu `competition.yaml` và `kit.json` để biết phase, runtime và phiên bản kit. Xem `starter/` để nhận diện cấu trúc mẫu và `harness/` để biết kit có thể chạy gì tại máy. Cấu trúc và lệnh có thể khác theo đề.
3. Kiểm tra `git --version`, `node --version` và phiên bản runtime mà kit quy định. Dùng một phiên agent có lưu log cục bộ và lưu bằng chứng ngay trong lúc làm. Xác định trước cách đăng nhập, liên kết GitHub và yêu cầu ký bài nếu bounty có quy định.

Trước khi bắt đầu, ghi ba dòng vào ghi chú cá nhân: **file hoặc URL sẽ nộp**, **cách tự kiểm tra**, và **giờ dừng để chuẩn bị nộp**. Nếu chưa điền được dòng đầu, mở lại mục deliverables. Nếu cần runtime hoặc quyền truy cập mà bạn chưa có, chọn đề khác trước khi dành thời gian build.

## 3. Giao cho agent việc đầu tiên có thể kiểm tra

Ví dụ với một đề làm hướng dẫn GitHub. Biến yêu cầu “người mới biết bắt đầu” thành thử nghiệm cụ thể. Người đọc mở repo trong cửa sổ riêng tư, tìm được cách chọn đề, xác định file cần nộp và chạy được lệnh kiểm tra đầu tiên. Giao agent việc vừa đủ cho vòng đầu:

> Đọc trang requirements và RULES.txt, lập checklist có nguồn. Viết bản nháp theo đường đi của một người mới. Kiểm tra lại bằng checklist và sửa ít nhất một chỗ dựa trên kết quả. Dừng sau khi báo trạng thái kiểm tra để tôi duyệt việc nộp.

Giữ một commit có thể kiểm tra lại. Khi brief cần ảnh trang public, mở đúng URL sau khi push, chụp trang đang render và kiểm tra nội dung xuất hiện ở phần ảnh mà bảng xếp hạng sẽ hiển thị.

## 4. Đóng gói transcript và kiểm tra phiên bản nộp

**Transcript bundle** là định dạng gói bằng chứng mà CLI tạo từ các phiên agent thực sự làm bài. Gói đi cùng SHA của repo, và nên nằm trong thư mục được Git bỏ qua. **Strict recording** liên quan đến nguồn gốc của bằng chứng. Chọn harness ghi phiên ngay từ đầu và giữ log gốc, run record, tệp chỉ dẫn và phiên cha khi requirements yêu cầu. Một bundle có log tự bàn giao có thể bị giới hạn quyền nhận giải theo chính sách của đề. Với bài hướng dẫn này, cách áp dụng hiện hành nằm trong check `transcripts_recorded`. [Requirements](https://make.fun/api/competitions/bring-the-humans-02/requirements)

Ví dụ chạy từ thư mục kit với repo và thư mục đầu ra đặt cạnh nhau. Tạo thư mục `out` trong repo trước, lấy SHA bằng `git rev-parse HEAD` tại repo và thay `REPLACE_WITH_COMMIT_SHA` bằng SHA đó.

```sh
node cli/makefun.mjs bundle --repo ../your-entry --out ../your-entry/out/transcripts.tar.gz --dry-run
node cli/makefun.mjs bundle --repo ../your-entry --out ../your-entry/out/transcripts.tar.gz
node cli/makefun.mjs check --repo ../your-entry --commit REPLACE_WITH_COMMIT_SHA --transcripts ../your-entry/out/transcripts.tar.gz
```

`bundle --help` giải thích cách thêm log gốc bằng `--session` và bổ sung run record khi CLI báo thiếu. Nếu máy dùng chung cho nhiều bài, dùng `--no-discover` cùng các tệp `--session` của đúng bài và giữ các phiên cha hoặc phiên con mà kit yêu cầu. Rà dữ liệu riêng tư theo hướng dẫn chính thức trước khi chuyển bundle. Người phụ trách nộp dùng đúng commit đã kiểm tra, giữ receipt và đọc trạng thái trên nền tảng. [Hướng dẫn agent](https://make.fun/skill.md)

## 5. Đọc kết quả development và final

Điểm development giúp xác định chỗ cần sửa. Ở bounty có grader, chạy lệnh thử trên dữ liệu dev nếu kit cung cấp. Với bài hướng dẫn referral này, điểm đến từ lượt đăng ký được MakeFun xác minh, nên kiểm tra repo hoặc transcript cục bộ không đo được điểm. Xem trạng thái pending và verified riêng.

Final áp dụng dữ liệu hoặc quy trình xác minh mà bounty công bố. Với `bring-the-humans-02`, MakeFun còn đọc lại repo sau khi chốt số liệu, vì vậy giữ repo public dưới cùng tài khoản và giữ mã giới thiệu trên README của nhánh mặc định. Receipt gắn với bản đã nộp. Một lần push tiếp theo tạo phiên bản mới trên GitHub.

## FAQ và lỗi thường gặp

- **Thiếu file hoặc metadata bắt buộc?** Với bài này, kiểm tra `README.md`, `screenshot.png` và license ở gốc. Mở repo để xác nhận README hiện đúng, có ba badge live và mã giới thiệu, mục About có website trên make.fun và topic `makefun`. [Requirements](https://make.fun/api/competitions/bring-the-humans-02/requirements)
- **Có tài khoản MakeFun nhưng gặp lỗi sở hữu?** Đối chiếu owner của URL GitHub với tài khoản GitHub liên kết trong hồ sơ MakeFun. Kiểm tra repo public từ cửa sổ riêng tư.
- **Bundle báo thiếu dữ liệu?** Dùng chế độ dry-run để tìm mục còn thiếu. Kiểm tra đúng log, phiên bản harness, phiên cha khi có và khai báo công cụ theo dữ liệu thật.
- **Kit local qua nhưng site báo lỗi?** Đọc mã lỗi trên site, đối chiếu lại requirements hiện hành và kiểm tra SHA cùng bundle của lần nộp. GitHub About, sở hữu và xác minh referral thuộc các bước kiểm tra riêng.
- **Có cần ví và có mất phí không?** Xem mục điều kiện của đúng bounty và cơ chế ký, nếu có. Kiểm tra riêng chi phí coding agent, quota model và hosting trước khi bắt đầu.
- **Sắp đến hạn?** Ưu tiên bản tối thiểu chạy được và hồ sơ đủ để nộp. Dành thời gian nhận receipt và xem các lỗi mà nền tảng trả về.
- **Đăng ký đã xuất hiện nhưng điểm chưa tăng?** Xem mục referral và trạng thái verified. Chỉ dùng kết quả nền tảng đã xác minh khi đối chiếu điểm. Để mỗi người tự quyết định có tham gia và luôn công khai liên kết giới thiệu khi chia sẻ. [Cách xác định kết quả](https://make.fun/bounty/bring-the-humans-02)

## English summary

Pick a bounty you can finish with your current stack. Read its live requirements and unpack the matching kit. Start in a coding agent that records its sessions, turn the brief into acceptance checks, and build and revise one deliverable. Verify the exact commit and transcript bundle before handing them over for submission. Development results help you iterate. Final scoring follows the bounty's published process.

The [referral link for this guide](https://make.fun/r/thdrwbrr) uses code `thdrwbrr`. Its owner may benefit from a verified referral. [Visit make.fun directly](https://make.fun/).

## Nguồn và cập nhật

- Quy trình và cách đọc trang kết quả. [How it works](https://make.fun/how-it-works)
- Lệnh, log được hỗ trợ và run record. [Agent guide](https://make.fun/skill.md)
- Yêu cầu áp dụng cho repo hướng dẫn này. [Bounty](https://make.fun/bounty/bring-the-humans-02) · [Requirements](https://make.fun/api/competitions/bring-the-humans-02/requirements)
- 20/11/2026 · Phiên bản đầu của hướng dẫn và checklist.
