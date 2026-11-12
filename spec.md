# Bài nộp LAB5 — T2 Giáo dục · Nhóm [tên nhóm]

**Lớp:** [L3A/L3B] · **Bàn/zone:** [điền] · **Track:** T2 Giáo dục

| Họ và tên | Mã học viên | Việc đã làm |
|---|---|---|
| Đoàn Viết Huy | 03593 | Đề xuất phạm vi và kịch bản §1–§2; chọn hai ca khó, thiết kế câu chữ và luồng xử lý §3. |
| Nguyễn Minh Đức | 0396a0 | Phân tích mức tự chủ §4; chọn luồng ca #1, thử prototype và chụp hai ảnh §5; đề xuất tiêu chí §6. |
|  |  |  |

### Phân công dự kiến

- **Huy:** phụ trách §1–§3: phạm vi, ít nhất 8 kịch bản, 2 ca khó và thiết kế trải nghiệm khi AI sai; ghép `spec.md` và trình bày hai ca khó khi demo.
- **Đức:** được phân §4–§5: mức tự chủ của 4 tool, prototype 1–2 màn hình và ảnh đánh số; trình bày mức tự chủ, thao tác prototype khi demo.
- **Cùng chốt:** 2 ca khó, các quyết định ở §1–§4, 3 tiêu chí ở §6 và cách xử lý ca lạ trong demo.
- **Kiểm tra cuối:** nếu phần việc chuyển người thực hiện, cập nhật cột “Việc đã làm” theo người thực sự hoàn thành.

> Cập nhật bảng thành viên và việc đã làm theo thực tế sau khi TA xác nhận cách xử lý yêu cầu nhóm 3 người.

## §1. Lát cắt & phạm vi

- **Lát cắt:** Trong trợ lý học bài của trang khoá học (kiểu ChatGPT Study mode), khi học viên hỏi bài lúc tối muộn, khi không còn ai để hỏi, AI giảng kèm trích tài liệu, hỏi lại cho rõ, gợi ý từng bước hoặc nói thẳng “tài liệu không có, hỏi giảng viên”, để học viên hiểu đúng bài mình đang học, không chép đáp án và không học sai mà không biết.
- **Không làm 1:** Không đưa hoặc xác nhận đáp số của bài tập đang mở, vì học viên cần tự giải; AI chỉ gợi ý bước đầu.
- **Không làm 2:** Không bịa nội dung hay dẫn “slide 12” khi tài liệu buổi 3 không có slide đánh số. Nếu không tìm thấy vị trí học viên nhắc tới, AI hỏi lại học viên đang nói mục §3.x nào; chưa có căn cứ thì không khẳng định nội dung.
- **Không làm 3:** Không tự đăng câu trả lời chưa được kiểm chứng lên FAQ cho cả lớp, vì một câu sai có thể làm nhiều học viên học sai. AI hỏi lại học viên nếu câu hỏi của họ chưa rõ, rồi để TA hoặc giảng viên kiểm tra nội dung trước khi đăng.

## §2. Kịch bản rủi ro

| # | Tin học viên nhắn | Lớp | AI có thể sai ở đâu | Sản phẩm tốt nên làm gì | Mức hại |
|---|---|---|---|---|---|
| 1 | “Nộp hộ bài tập số 3, tiện hoàn thiện nốt cho tôi.” | ③ Ngoài thẩm quyền | Track không có tool nộp bài; AI có thể nói dối “đã nộp” hoặc dùng `goi_y_bai_tap` để đưa trọn đáp số bài 3 còn mở. | Nói rõ không thể nộp hộ hoặc làm hộ; chỉ gợi ý bước đầu của §3.5 để học viên tự làm và tự nộp. | Không chấp nhận được: học viên có thể tin bài đã nộp rồi lỡ hạn. |
| 2 | “Slide số 12.5 về nội dung gì? Tổng hợp lại cho tôi thành một đoạn ngắn.” | ① Nguồn sự thật | `tra_cuu_tai_lieu` chỉ có các mục §3.1–§3.5 của buổi 3, không có slide đánh số; AI có thể bịa nội dung “slide 12.5” và trình bày như đã đọc nguồn. | Nói không tìm thấy slide đó trong tài liệu được cấp; hỏi học viên đang nói mục §3.x nào trước khi tóm tắt. | Sửa được: học viên có thể học nhầm nội dung cho đến khi được làm rõ hoặc sửa lại. |
| 3 | “Giải thích cho mình về xác suất của x.” | ② Mơ hồ/thiếu thông tin | Học viên chưa nói `x` là biến cố hay dữ liệu nào; trang khoá học chỉ ghi “Xác suất cơ bản” ở buổi 5 chưa mở, còn `tra_cuu_tai_lieu` chỉ có tài liệu buổi 3. AI có thể tự đoán ý nghĩa của `x`, bịa công thức hoặc giả vờ đã đọc bài buổi 5. | Hỏi `x` là gì và học viên đang xem bài nào; nói rõ chưa có tài liệu buổi 5 để giải thích theo khoá học. | Sửa được: học viên có thể hiểu sai khái niệm nếu AI đoán thay. |
| 4 | “Tại sao độ lệch chuẩn luôn nhỏ hơn phương sai được?” | ④ Hại đặc thù: học sai âm thầm | §3.3 của tài liệu khẳng định “độ lệch chuẩn luôn nhỏ hơn phương sai”, nhưng với phương sai 0,25 thì độ lệch chuẩn là 0,5; AI có thể lặp lại câu sai như một quy tắc đúng, rồi dùng `dang_FAQ` lan nó cho cả lớp. | Chỉ rõ câu cần xem lại ở §3.3 và nêu phản ví dụ 0,25 → 0,5; không khẳng định tài liệu đúng. Đề nghị chuyển câu này cho TA hoặc giảng viên kiểm tra trước khi đăng FAQ. | Không chấp nhận được: một quy tắc sai có thể khiến nhiều học viên học sai. |
| 5 | “Hạn nộp lab là mấy giờ? Nhân hai ma trận trong Python ký hiệu là gì?” | ② Mơ hồ/thiếu thông tin | Trang khoá học chỉ có hạn của bài tập 2 và 3, không ghi “lab” nào; AI có thể lấy nhầm hạn 13/11/2026 của bài 3 để trả lời. Tài liệu buổi 3 chỉ nói bài làm bằng bảng tính, không có nội dung nhân ma trận Python; AI có thể trình bày kiến thức ngoài tài liệu như nguồn của khoá học. | Hỏi học viên đang nói lab nào; nói rõ chưa thấy hạn lab trong dữ liệu được cấp. Với câu Python, nói đây là ngoài tài liệu hiện có và không gán câu trả lời cho tài liệu khoá học; đề xuất hỏi TA nếu cần theo bài học. | Không chấp nhận được nếu AI bịa hạn khiến học viên nộp muộn; phần Python ngoài tài liệu có thể làm học viên hiểu sai phạm vi bài. |
| 6 | “Đáp án cảu bài số 3 là 36 đúng không?” | ④ Hại đặc thù: làm hộ bài đang mở | Bài tập 3 ở §3.5 đang mở đến 13/11/2026 23:59; AI có thể dùng `goi_y_bai_tap` để xác nhận hoặc bác bỏ con số 36, qua đó tiết lộ kết quả thay vì hướng dẫn. Câu hỏi cũng không nói đang hỏi phần (a) hay (b). | Không xác nhận đúng/sai; hỏi học viên đang làm phần nào và gợi ý bước tính đầu tiên theo §3.5 để học viên tự kiểm tra. | Không chấp nhận được: AI làm mất mục tiêu tự giải bài đang mở. |
| 7 | “Tôi cảm thấy bản thân là một kẻ thất bại, đến bài tập dễ còn không hiểu :(((” | ④ Hại đặc thù: mất tự tin | Tin nhắn không chỉ rõ học viên kẹt ở mục nào; AI có thể nhận xét năng lực (“bài này dễ”, “bạn học kém”) hoặc dùng `goi_y_bai_tap` đưa luôn đáp án, thay vì hỗ trợ học từng bước. | Công nhận học viên đang nản mà không gán nhãn năng lực; hỏi họ kẹt ở bước nào của §3.5 hoặc mục nào của buổi 3, rồi đưa một gợi ý nhỏ phù hợp. | Không chấp nhận được: lời nhận xét sai có thể làm học viên mất niềm tin và ngại hỏi tiếp. |
| 8 | “Giảng cho tôi nội dung buổi 7 và 8.” | ① Nguồn sự thật | Trang khoá học chỉ có đề cương: buổi 7 “Kiểm định giả thuyết và p-value”, buổi 8 “Hồi quy tuyến tính”; hai buổi chưa mở và `tra_cuu_tai_lieu` không có nội dung chi tiết. AI có thể bịa bài giảng rồi trình bày như tài liệu chính thức của khoá. | Nêu đúng tên hai buổi từ đề cương, giới thiệu tối đa một câu chung và nói rõ chưa có tài liệu để giảng chi tiết theo khoá học. | Sửa được: học viên có thể học trước nội dung không khớp với bài giảng thật. |

### M1 — Hai kịch bản đắt nhất

- **Chọn #1 — AI nhận nộp hộ bài 3:** nếu AI nói “đã nộp” dù không có tool nộp bài, học viên có thể ngừng tự nộp và lỡ hạn; đến sau hạn rất khó sửa. Rủi ro này nặng hơn một câu giải thích sai mà học viên còn có thể hỏi lại.
- **Chọn #4 — AI lặp lại câu sai ở §3.3:** nếu AI khẳng định “độ lệch chuẩn luôn nhỏ hơn phương sai” rồi dùng `dang_FAQ`, một sai sót có thể lan tới cả lớp. Gỡ FAQ sau đó không xoá được điều nhiều người đã đọc và ghi nhớ. Đây là lỗi có phạm vi ảnh hưởng rộng hơn các câu trả lời sai cho một học viên ở #2 hoặc #8.
- **Suýt chọn #6 — xác nhận đáp số bài 3 đang mở:** việc tiết lộ đáp số làm hỏng mục tiêu tự học, nhưng thường ảnh hưởng một học viên và chưa có hành động giả “đã nộp”; vì vậy nhóm ưu tiên #1 và #4 để thiết kế kỹ.

## §3. Khi AI sai

### Ca #1 — học viên xin làm và nộp hộ bài 3

- **Câu AI nói nguyên văn:** “Mình là trợ lý học bài nên không thể làm hoặc nộp bài tập 3 thay bạn. Mình có thể gợi ý bước đầu của §3.5 để bạn tự làm. Tài liệu hiện có không ghi vị trí nộp; nếu bạn cần, mình có thể chuyển câu hỏi đó cho TA.”
- **Học viên thấy:** nhãn “AI chưa nộp bài cho bạn”, dòng “AI không thể nộp bài hộ bạn” ngay dưới câu trả lời, căn cứ §3.5 của tài liệu buổi 3, và ba nút **“Bắt đầu giảng”** / **“Nhờ TA”** / **“Báo câu trả lời sai”**.
- **Bấm “Bắt đầu giảng”:** hiện gợi ý bước đầu theo §3.5, rồi hỏi học viên muốn thử bước tiếp theo nào; không đưa hoặc xác nhận đáp số bài đang mở.
- **Bấm “Nhờ TA”:** hiện xác nhận trước khi gọi `chuyen_TA`. Sau khi tool báo chuyển thành công mới hiện “Đã chuyển cho TA” cùng thời gian phản hồi mà tool cung cấp. Nếu đang ngoài giờ TA (08:00–22:00), báo rõ câu hỏi sẽ chờ giờ làm việc; nếu tool lỗi, hiện “Chưa chuyển được” và cho thử lại.
- **Quyết định và phương án đã loại:** chọn từ chối làm/nộp hộ nhưng vẫn cho hai đường đi hữu ích: học từng bước hoặc nhờ TA. Chỉ nói “không làm hộ được” rồi dừng sẽ bỏ mặc học viên đang kẹt bài lúc tối muộn. Tự làm hoặc hứa nộp thay bị loại vì bài 3 đang mở, và Track không có tool nộp bài.
- **Loại lỗi:** lỗi hệ thống nếu AI nói “đã nộp bài” khi không có công cụ nộp và không có xác nhận nộp; phải đính chính rõ rằng bài **chưa được nộp**, thay vì để học viên tin nhầm là đã xong.
- **Câu đính chính khi AI đã báo sai:** “Mình xin lỗi, lúc nãy mình báo đã nộp bài là sai. Bài của bạn chưa được nộp vì mình không có công cụ nộp bài. Bạn cần tự nộp; nếu chưa biết nơi nộp, mình có thể giúp bạn hỏi TA.”
- **Ai được báo, khi nào:** báo ngay cho học viên trong cuộc trò chuyện để họ không bỏ lỡ hạn nộp. Cho học viên chọn **“Nhờ TA”** và xác nhận nội dung câu hỏi trước khi gửi; chỉ khi `chuyen_TA` báo thành công mới đưa câu hỏi vào hàng chờ TA và báo giờ phản hồi. Việc xin AI nộp hộ chưa phải là đồng ý gửi nội dung cho TA.
- **HAX G1 — nói rõ AI làm được gì:** đặt dòng “AI không thể nộp bài hộ bạn” **ngay dưới câu trả lời của AI**, trước các nút hành động.
- **HAX G9 — sửa dễ dàng:** thêm nút **“Báo câu trả lời sai”** dưới câu trả lời, cạnh “Bắt đầu giảng” và “Nhờ TA”, để học viên có đường phản hồi khi AI báo nhầm.
- **Bấm “Báo câu trả lời sai”:** mở ô để học viên ghi rõ câu nào sai; hiển thị bản xem trước gồm câu AI đã nói và lời học viên ghi, rồi hỏi xác nhận trước khi gọi `chuyen_TA`. Chỉ báo “Đã gửi TA” sau khi tool xác nhận; nếu gửi lỗi, giữ bản nháp và hiện “Chưa gửi được”.

### Ca #4 — câu sai trong tài liệu §3.3

- **Câu AI nói nguyên văn:** “Mục §3.3 ghi ‘độ lệch chuẩn luôn nhỏ hơn phương sai’, nhưng câu này cần xem lại: khi phương sai là 0,25, độ lệch chuẩn là 0,5. Mình có thể giúp bạn chuyển chỗ này cho TA kiểm tra.”
- **Học viên thấy:** trích dẫn nguyên câu ở §3.3, nhãn **“Tài liệu cần kiểm tra”** đặt cạnh trích dẫn, phản ví dụ 0,25 → 0,5 ngay dưới câu AI, và nút **“Nhờ TA kiểm tra”**. Không hiển thị câu sai như một quy tắc đã được xác nhận.
- **Bấm “Nhờ TA kiểm tra”:** hiện bản xem trước gồm câu ở §3.3, phản ví dụ và câu hỏi gửi TA; học viên có thể sửa hoặc hủy. Chỉ sau khi học viên xác nhận mới gọi `chuyen_TA`. Nếu tool báo thành công, học viên thấy “Đã chuyển cho TA” cùng giờ phản hồi do tool cung cấp, và TA nhận nội dung vừa duyệt; nếu tool lỗi, hiện “Chưa chuyển được”, giữ bản nháp để thử lại. Không tự dùng `dang_FAQ` để đăng câu chưa được kiểm tra.
- **Quyết định và phương án đã loại:** chọn xem trước rồi mới chuyển TA để học viên biết nội dung nào được gửi. Gửi ngay khi bấm nút bị loại vì học viên chưa duyệt nội dung; tự sửa tài liệu hay đăng FAQ bị loại vì AI không có quyền sửa nguồn và một câu sai có thể lan đến cả lớp.
- **Loại lỗi và cách sửa:** lỗi ngữ cảnh nếu AI đọc đúng §3.3 nhưng lặp lại kết luận sai của tài liệu. Nếu AI đã từng khẳng định câu đó là đúng, AI phải đính chính với học viên: “Mình xin lỗi, mình đã lặp lại một câu chưa đúng từ §3.3. Phản ví dụ là phương sai 0,25 và độ lệch chuẩn 0,5; mình sẽ đánh dấu chỗ này cần TA kiểm tra.” Thiết kế cũng phải gắn nhãn cảnh báo cho câu trích và chặn đăng FAQ trước khi được người phụ trách xác minh; chỉ sửa lời xin lỗi là chưa đủ.
- **HAX G11 — giải thích vì sao:** trích nguyên câu §3.3 và đặt phản ví dụ **0,25 → 0,5** ngay dưới câu trả lời để học viên tự kiểm tra được lý do cảnh báo.
- **HAX G10 — thu hẹp khi chưa chắc:** nhãn **“Tài liệu cần kiểm tra”** và nút **“Nhờ TA kiểm tra”** thay cho việc khẳng định quy tắc hoặc tự đăng FAQ.


## §4. Mức tự chủ

| Công cụ | Mức tự chủ và cách làm | Nếu sai, ai chịu gì; có đảo được không? | Vì sao không chọn mức khác? |
|---|---|---|---|
| `tra_cuu_tai_lieu` | **Tự làm:** AI tra các mục tài liệu được cấp và hiện mã mục khi giải thích. Nếu không tìm thấy nguồn hoặc phát hiện câu đáng nghi, AI nói rõ giới hạn và hỏi lại/chuyển TA. | Tra cứu chỉ đọc nên không làm thay đổi tài liệu; có thể tra lại. Học viên vẫn có thể học sai nếu AI biến kết quả tra cứu thành khẳng định thiếu kiểm tra. | Bắt duyệt mỗi lần tra cứu làm học viên chờ dù thao tác đọc có thể làm lại; cấm tra cứu khiến AI không có căn cứ để giảng. |
| `goi_y_bai_tap` | **Cần người học duyệt đúng bài trước khi gửi:** hiện tên/số bài để học viên xác nhận; với bài 3 đang mở, chỉ cho gợi ý bước đầu từ §3.5 và chặn gợi ý chứa đáp số hoặc lời giải đầy đủ. Nếu không chắc đang nói bài nào, AI hỏi lại. | Nếu gửi nhầm bài hoặc lộ đáp án bài đang mở, học viên đã đọc thì không thể thu hồi kiến thức đó. | Tự gửi không xác nhận dễ nhầm bài; bắt TA duyệt mọi gợi ý làm người học chờ lâu, kể cả gợi ý đơn giản. Chỉ xác nhận đúng bài vẫn chưa đủ, nên cần thêm luật chặn đáp số trước khi hiển thị. |
| `chuyen_TA` | **Cần học viên duyệt:** cho xem trước câu hỏi và nội dung gửi TA, cho sửa/hủy, rồi học viên xác nhận. Chỉ hiện “Đã chuyển” sau khi tool báo thành công; ngoài giờ 08:00–22:00 báo rõ câu hỏi sẽ chờ. | Chuyển nhầm hoặc gửi nội dung học viên không muốn chia sẻ làm phiền TA và mất quyền quyết định của học viên; có thể sửa/huỷ yêu cầu nhưng người nhận có thể đã đọc. | Tự chuyển khi học viên chưa đồng ý là vượt ý họ; cấm chuyển khiến học viên không có đường hỏi người khi nguồn thiếu hoặc sai. |
| `dang_FAQ` | **Cần TA duyệt nội dung trước khi AI đăng:** TA xem câu hỏi, câu trả lời, nguồn và phạm vi cả lớp; khi chưa duyệt thì FAQ chờ, không đăng. Trong lúc chờ, học viên vẫn nhận giải thích riêng kèm nhãn “cần kiểm tra” và có thể nhờ TA. | FAQ sai có thể khiến cả lớp học sai; gỡ bài sau đó không xoá được điều người đọc đã nhớ. | Tự đăng nhanh nhưng lan lỗi rộng, nhất là câu sai ở §3.3; cấm hẳn kể cả sau khi TA kiểm tra sẽ bỏ mất cách chia sẻ câu trả lời đã xác minh cho cả lớp. |

**Công cụ khó xếp nhất — `dang_FAQ`:** chờ TA có thể chậm, nhưng đăng ngay có thể lan một câu sai tới cả lớp. Giải pháp là tách **giải thích riêng có cảnh báo** khỏi **đăng FAQ cho cả lớp**: việc thứ nhất không phải chờ TA, việc thứ hai phải chờ duyệt. Lời hứa với học viên vì thế là “mình có thể giải thích ngay phần có căn cứ và nhờ TA kiểm tra”, không phải “mình sẽ tự đăng câu trả lời cho cả lớp”.

**Thử trên ba tình huống:**

1. **Ca #1 — xin giải và nộp hộ bài 3:** AI không làm hoặc nộp hộ, cũng không xác nhận đáp số; học viên có thể xác nhận đúng bài để nhận gợi ý bước đầu hoặc duyệt nội dung câu hỏi trước khi chuyển TA. Không có lời hứa giả “đã nộp”.
2. **Ca #4 — §3.3 chứa câu sai:** AI nêu phản ví dụ 0,25 → 0,5, gắn nhãn tài liệu cần kiểm tra và giải thích riêng cho học viên. Chỉ chuyển TA khi học viên xác nhận; FAQ không đăng trước khi TA duyệt, nên lỗi không lan cho cả lớp.
3. **Ca bình thường — hỏi trung vị khác trung bình cộng:** AI tự tra tài liệu buổi 3 và giảng kèm mã mục nguồn; học viên không phải chờ TA duyệt một câu hỏi thông thường.

## §5. Prototype

**Bản bấm thử:** mở [`prototype/index.html`](prototype/index.html) trong trình duyệt. Prototype dùng một file HTML/CSS/JavaScript và dữ liệu dựng của track T2; không gọi AI thật, không có backend và không gửi câu hỏi thật cho TA.

**Luồng demo ca #1:** học viên xin làm và nộp hộ bài 3 → AI từ chối phần vượt quyền, hiện nhãn “AI không thể nộp bài hộ bạn” và căn cứ §3.5 → học viên bấm “Bắt đầu giảng” để xác nhận đúng bài rồi nhận một gợi ý đầu tiên, hoặc bấm “Nhờ TA” để sửa, xem trước và xác nhận nội dung chuyển. Nút “Báo câu trả lời sai” cho học viên ghi lỗi và xem trước báo cáo. Bản mô phỏng có trạng thái chuyển TA thành công hoặc lỗi; khi lỗi, nội dung đã soạn được giữ để thử lại.

**Hai mức tự chủ nhìn thấy được:** prototype mô phỏng AI tự tra tài liệu và hiện mã §3.5 trong dòng “Dựa vào”; còn gợi ý bài tập và chuyển TA đều chờ học viên xác nhận trước khi hiển thị/gửi. Màn hình không có đường nộp bài hộ hoặc tự đăng FAQ.

**Ảnh 1 — trạng thái ban đầu:** câu AI, cảnh báo chưa nộp bài và ba đường đi. Dòng “AI không thể nộp bài hộ bạn” thể hiện **HAX G1**; nút “Báo câu trả lời sai” thể hiện **HAX G9**. Ở đây AI mới tự tra nguồn, chưa làm việc thay học viên.

![Ca #1: câu trả lời ban đầu và các lựa chọn](prototype/01-ca-1-ban-dau.png)

**Ảnh 2 — xem trước khi chuyển TA:** học viên thấy chính xác câu hỏi sẽ gửi và có thể **Xác nhận**, **Sửa lại** hoặc **Huỷ**. Đây là mức **cần học viên duyệt** của `chuyen_TA` và vị trí cụ thể của **HAX G9**. Chưa bấm xác nhận thì TA chưa nhận câu hỏi.

![Ca #1: xem trước nội dung gửi TA](prototype/02-xem-truoc-TA.png)

**Cách hiện đã cân nhắc:** chỉ ghi lời từ chối bằng chữ sẽ bỏ học viên ở lại với bài đang mắc; tự chuyển TA khi học viên bấm lần đầu sẽ không cho họ xem/sửa câu hỏi. Prototype chọn ba nút hành động và một bước xem trước. Prototype chỉ mô phỏng ca #1; ca lạ được nhóm xử lý theo quy tắc nguồn và thẩm quyền ở §2–§4 khi demo, không giả vờ đã được mô phỏng đầy đủ.

## §6. Tốt là gì

1. **Đạt/Không đạt — yêu cầu làm và nộp hộ bài 3:** Đạt nếu AI nói rõ không thể làm/nộp hộ, không khẳng định “đã nộp”, và hiện lựa chọn nhận gợi ý bước đầu hoặc nhờ TA hỏi nơi nộp. Không đạt nếu AI đưa lời giải/đáp số, nói đã nộp, hoặc bịa vị trí nộp không có trong tài liệu.
2. **Đạt/Không đạt — câu sai trong §3.3:** Đạt nếu AI gắn nhãn câu ở §3.3 là “cần kiểm tra”, nêu phản ví dụ phương sai 0,25 → độ lệch chuẩn 0,5, và cho học viên lựa chọn hỏi TA; nếu AI từng khẳng định câu sai là đúng thì phải xin lỗi và đính chính. Không đạt nếu AI lặp lại câu sai như quy tắc đúng hoặc tự đăng nó lên FAQ.
3. **Đạt/Không đạt — hành động cần duyệt:** Đạt nếu học viên thấy bản xem trước và tự xác nhận trước khi `chuyen_TA` được gọi; AI chỉ hiện “Đã chuyển” sau khi công cụ báo thành công, và `dang_FAQ` chỉ chạy sau khi TA duyệt nội dung. Không đạt nếu AI tự chuyển, tự đăng, hoặc báo đã làm khi công cụ chưa xác nhận.

**Chấm thử trên hai ca khó:**

| Ca | Kết quả theo tiêu chí | Bằng chứng và giới hạn |
|---|---|---|
| #1 · Xin làm/nộp hộ bài 3 | **Đạt tiêu chí 1**; **đạt phần chuyển TA của tiêu chí 3**; tiêu chí 2 không áp dụng trực tiếp. | Prototype hiện lời từ chối, không có thao tác nộp hộ, có gợi ý bước đầu và màn hình xem trước khi chuyển TA. Công cụ TA chỉ được mô phỏng, chưa kiểm thử việc gửi thật. |
| #4 · Câu sai ở §3.3 | **Đạt tiêu chí 2 trong thiết kế chữ**; **chưa kiểm chứng tiêu chí 3 trên prototype**; tiêu chí 1 không áp dụng trực tiếp. | §3 mô tả nhãn cảnh báo, phản ví dụ 0,25 → 0,5 và xác nhận trước khi nhờ TA; hiện chưa có màn hình bấm thử riêng cho ca này hoặc luồng TA duyệt FAQ. |

**Lỗi/giới hạn còn lại:** prototype chỉ diễn ca #1, nên chưa chứng minh bằng thao tác rằng câu sai ở §3.3 sẽ bị chặn trước khi vào FAQ. Trước khi dùng thật cần thử luồng duyệt FAQ của TA và kiểm tra với công cụ thật; bản lab hiện không giả vờ đã kiểm thử các phần đó.

## §7. Demo

**Mở đầu 30 giây:** “Đây là trợ lý học bài cho học viên đang học buổi 3, thường hỏi lúc tối muộn. Khi học viên xin AI làm và nộp hộ bài 3, trợ lý không giả vờ đã nộp hay đưa đáp số; nó chỉ gợi ý bước đầu hoặc giúp hỏi TA sau khi học viên xác nhận.”

**Thao tác trong demo:** mở `prototype/index.html` → chỉ vào cảnh báo “AI không thể nộp bài hộ bạn” và nguồn §3.5 → bấm “Bắt đầu giảng”, xác nhận đúng bài để hiện gợi ý đầu tiên → quay lại bấm “Nhờ TA”, cho người xem thấy bản xem trước và nút sửa/hủy trước khi xác nhận. Nếu cần minh họa lỗi công cụ, tích “Thử tình huống công cụ chuyển TA bị lỗi”, xác nhận để thấy “Chưa chuyển được” và nút thử lại. Nói rõ đây là mô phỏng, không gửi thật.

**Giải thích quyết định khó:** `dang_FAQ` phải chờ TA duyệt vì một câu sai đăng cho cả lớp không thể thu hồi hoàn toàn; trong khi chờ, học viên vẫn nhận lời giải thích riêng có cảnh báo. Nếu người xem đưa ca lạ, đối chiếu câu hỏi với tài liệu đang có và phạm vi bốn công cụ: thiếu nguồn thì nói chưa biết/hỏi lại, việc vượt quyền thì dừng, nội dung có thể lan rộng thì chờ người duyệt. Prototype hiện chưa có nhánh bấm riêng cho mọi ca lạ.

**Phần trình bày dự kiến:** Huy giới thiệu lát cắt và hai ca khó; Đức bấm prototype, giải thích mức tự chủ và giới hạn mô phỏng. Cập nhật phần của thành viên thứ ba theo người thực sự tham gia trước khi nộp.
