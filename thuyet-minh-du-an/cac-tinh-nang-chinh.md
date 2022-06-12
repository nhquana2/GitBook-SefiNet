# Các tính năng chính

### Cơ sở dữ liệu website an toàn & kém an toàn

Hệ thống cơ sở dữ liệu phân loại các website an toàn và kém an toàn. **SefiNet** sẽ cập nhật nhanh nhất có thể khi thực hiện phân loại các địa chỉ web thường được truy cập vào 2 mục trên.

#### Khi truy cập vào một website nhưng không chắc chắn về mức độ an toàn, đáng tin cậy của website đó, người dùng có thể:

* Tìm kiếm website trong bảng cơ sở dữ liệu hiện có theo tên miền.
* Xem các thông tin chi tiết về website đó, bao gồm:
  * _**Tên miền.**_
  * _**Mức độ nguy hiểm**_ (có 3 mức độ: Cao, Trung bình, Thấp - áp dụng đối với website thuộc phân loại kém an toàn).
  * _**Mức độ tin cậy**_ (có 3 mức độ: Cao, Trung bình, Thấp - áp dụng đối với website thuộc phân loại an toàn).
  * _**Hình thức:**_
    * Đối với website kém an toàn, chúng tôi phân loại hình thức như sau: Phishing, Phần mềm độc hại, Giả mạo, Đánh bạc trực tuyến, Đồi trụy, xuyên tạc, Tấn công, Chiếm đoạt tài sản, Khác.
    * Đối với website an toàn, có thể có nhiều hình thức đa dạng khác nhau hướng đến nội dung website (ví dụ: Tin tức, Công cụ tìm kiếm,...).
  * _**Mô tả chi tiết.**_
  * _**Đối tượng lừa đảo:**_ Đơn vị/ cá nhân/ tổ chức quản lý website thực hiện hành vi lừa đảo (áp dụng đối với website thuộc phân loại kém an toàn).
  * _**Người quản lý:**_ Đơn vị/ cá nhân/ tổ chức quản lý website này (áp dụng đối với website thuộc phân loại an toàn).
  * _**Hình ảnh:**_ Ảnh chụp website theo mốc thời gian cụ thể.
  * _**Ảnh chụp nhanh (live preview):**_ Ảnh chụp website theo thời gian thực (khi người dùng bấm xem thông tin chi tiết) sử dụng API của _Thum.io_.

Tuy nhiên, một số website có thể không được cập nhật kịp thời vì số lượng quá nhiều, người dùng có thể xem độ đánh giá tin cậy (theo thang điểm 100) của extension được đánh giá tự động.

Ngoài ra, **SefiNet** khuyến khích người dùng điền vào [_biểu mẫu báo cáo bổ sung dữ liệu website_](https://sefinet.top/bao-cao-bo-sung-du-lieu-website/) (trong trường hợp website chưa có trong CSDL) để **SefiNet** thực hiện đánh giá thủ công và thêm vào cơ sở dữ liệu. Việc báo cáo bổ sung website vào CSDL giúp bảo vệ bạn và mọi người tốt hơn.

**Tiêu chí và quy trình đánh giá:**

{% tabs %}
{% tab title="First Tab" %}
|                                 Tiêu chí                                | Điểm cộng                                                                                                                                                                                                                                                   | Điểm trừ                                                                                                                                                                                                                                                                                                                                                                                                                                                                             |
| :---------------------------------------------------------------------: | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
|                                 Tên miền                                | Đuôi tên miền trả phí (.com, .net, .org, .info, .me, .top, các đuôi tên miền cấp quốc gia,...) **+5 điểm**                                                                                                                                                  | Đuôi tên miền miễn phí (.tk, .ml, .ga, .cf, .gq, .cu.cc, .cz.cc, .co.nf, .co.nr,...) **-8 điểm**                                                                                                                                                                                                                                                                                                                                                                                     |
|                                 Máy chủ                                 | <ul><li>Có sử dụng dịch vụ DNS trung gian (VD: Cloudflare) <strong>+5 điểm</strong></li><li>IP máy chủ sạch, không host cùng các website kém an toàn nào <strong>+5 điểm</strong></li></ul>                                                                 | <ul><li>IP máy chủ host cùng các website kém an toàn <strong>-10 điểm</strong></li><li>Thường xuyên downtime do máy chủ không ổn định <strong>-5 điểm</strong></li></ul>                                                                                                                                                                                                                                                                                                             |
|                                   SSL                                   | <ul><li>Domain Validation SSL <strong>+6 điểm</strong></li><li>Organization Validation SSL <strong>+10 điểm</strong></li><li>Extended Validation SSL <strong>+20 điểm</strong></li></ul>                                                                    | Không có chứng chỉ SSL, chứng chỉ không hợp lệ, hết hạn **-10 điểm**                                                                                                                                                                                                                                                                                                                                                                                                                 |
|                               Nội dung thô                              | <ul><li>Văn phong chuẩn mực, đúng chính tả <strong>+5 điểm</strong></li><li>Bài viết chất lượng, không copy từ trang khác <strong>+10 điểm</strong></li><li>Không chứa bất kỳ nội dung kém an toàn nào như mục bên phải <strong>+15 điểm</strong></li></ul> | <ul><li>Bài viết kém chất lượng, copy từ trang khác <strong>-8 điểm</strong></li><li>Chứa <strong></strong> nội dung spam, đồi truỵ, xuyên tạc, đa cấp, đánh bạc <strong>-35 điểm</strong></li><li>Có dấu hiệu phishing, giả mạo, yêu cầu thông tin cá nhân, tài chính của người dùng như trang thật (có thể kiểm tra nhanh thông qua domain) <strong>-50 điểm</strong></li><li>Cung cấp phần mềm cr@ck, chứa virus, các hình thức tấn công mạng <strong>-35 điểm</strong></li></ul> |
|                         Nội dung đa phương tiện                         | <ul><li>Hình ảnh, video,... phù hợp, an toàn <strong>+5 điểm</strong></li><li>Hình ảnh, video,... sáng tạo, đẹp mắt, có sự đầu tư <strong>+5 điểm</strong></li></ul>                                                                                        | Hình ảnh, video,... mang tính chất đồi truỵ, xuyên tạc, đa cấp, đánh bạc **-20 điểm**                                                                                                                                                                                                                                                                                                                                                                                                |
|                          Báo cáo của người dùng                         | **+2 điểm/ 1 lượt** báo cáo an toàn hợp lệ                                                                                                                                                                                                                  | **-3 điểm/ 1 lượt** báo cáo kém an toàn hợp lệ                                                                                                                                                                                                                                                                                                                                                                                                                                       |
| Đánh giá của Site Safety Trend Micro (được đánh giá xét duyệt thủ công) | <ul><li>Được đánh giá thuộc các danh mục an toàn <strong>+15 điểm</strong></li><li>Chưa được đánh giá (untested) <strong>+0 điểm</strong></li></ul>                                                                                                         | Được đánh giá thuộc các danh mục kém an toàn, nguy hiểm **-20 điểm**                                                                                                                                                                                                                                                                                                                                                                                                                 |
{% endtab %}

{% tab title="Second Tab" %}

{% endtab %}
{% endtabs %}

### Kiểm tra kiến thức an toàn thông tin

_Tính năng chưa hoàn thiện_

Người dùng có thể thực hiện các bài kiểm tra kiến thức tương tự với việc thực hành nhận biết website là đáng tin cậy hay lừa đảo, giả mạo.

Một câu hỏi sẽ bao gồm:

* Hình chụp, hoặc file HTML được render kèm định dạng mô phỏng lại website thực tế.
* Đáp án là một trong 2 lựa chọn: _**Thật** hay **Giả mạo**._

Bên cạnh đó, người dùng có thể xem qua các ví dụ minh họa của **SefiNet** trước khi làm bài kiểm tra kiến thức.

### Blog chia sẻ kiến thức

**SefiNet** có chia sẻ các kiến thức, thông tin có liên quan đến an toàn thông tin và một số lĩnh vực khác thông qua các bài viết trên blog. Các bài viết này do đội ngũ tác giả và đồng tác giả tự biên soạn, đảm bảo rằng các bài viết cô đọng và dễ hiểu cho người dùng.

#### Các bài viết được chia ra thành các chuyên mục:

* **Thông báo:** Thông báo chung liên quan đến SefiNet.
* **Bảo mật:** Các bài viết liên quan đến vấn đề bảo mật thông tin.
* **Tin tức:** Cập nhật tin tức (về các vụ việc lừa đảo, giả mạo, thông tin cập nhật bảo mật của các dịch vụ phổ biến,...).
* **Khác:** Các bài viết thuộc các lĩnh vực khác.

### Extension kiểm soát truy cập Internet

_Tính năng chưa hoàn thiện_

Extension (tiện ích) được tích hợp trên trình duyệt nhân Chromium, hỗ trợ kiểm soát và hạn chế bạn truy cập các website kém an toàn. Đồng thời đánh giá tự động độ tin cậy của website (trên thang điểm 100) dựa trên các tiêu chí xác định _(dự kiến)_.
