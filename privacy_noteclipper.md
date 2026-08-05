# Chính sách quyền riêng tư — Notion Auto-Save & Note Clipper

**Cập nhật lần cuối: 05/08/2026**

Tài liệu này áp dụng cho tiện ích Chrome **Notion Auto-Save & Note Clipper**
(mã mặt hàng trên Chrome Web Store: `glbhgbclpmfjlilapionmemkomhnpokp`).

> Bản tiếng Anh nằm ở [cuối trang](#privacy-policy--notion-auto-save--note-clipper-english).

---

## 1. Tóm tắt

- Tiện ích **không có server riêng**. Không có backend nào do nhà phát triển
  vận hành đứng giữa bạn và Notion.
- Tiện ích **không thu thập, không bán, không chia sẻ dữ liệu của bạn** cho
  bất kỳ bên thứ ba nào ngoài Notion — và chỉ khi chính bạn bấm nút lưu.
- Không có công cụ phân tích (analytics), không theo dõi hành vi, không
  quảng cáo.
- Mọi dữ liệu tạo ra khi bạn dùng tiện ích chỉ đi tới **hai nơi**: ổ đĩa cục
  bộ của bạn (qua `chrome.storage.sync`, cơ chế đồng bộ của chính Google Chrome)
  và **api.notion.com** — dùng token Notion do chính bạn tạo ra và dán vào.

## 2. Dữ liệu nào được xử lý

| Dữ liệu | Khi nào được đọc | Đi đâu |
|---|---|---|
| Notion integration token (secret) | Bạn tự dán vào trang Cài đặt | Lưu tại `chrome.storage.sync`; gửi kèm mỗi request tới `api.notion.com` để xác thực |
| ID và tên database Notion bạn chọn | Sau khi bạn chọn hoặc tạo database | Lưu tại `chrome.storage.sync` |
| Đoạn text bạn **chủ động bôi đen** trên trang web | Khi bạn bấm nút lưu / chuột phải / mở popup | Gửi tới `api.notion.com` để tạo trang mới trong database của bạn |
| Tiêu đề và URL của tab đang mở | Khi bạn bấm lưu | Gửi tới `api.notion.com` làm thuộc tính của trang mới |
| Tag, ghi chú, trạng thái bạn nhập trong popup | Khi bạn gõ vào form | Gửi tới `api.notion.com` |

Tiện ích **không** đọc nội dung trang khi bạn không bôi đen text và không chủ
động bấm lưu. Content script chỉ chạy để hiển thị nút lưu nổi cạnh vùng chọn
và toast thông báo — nó không quét, không sao chép nội dung trang trong nền.

## 3. Dữ liệu được lưu ở đâu

- **`chrome.storage.sync`**: cơ chế lưu trữ do Google Chrome cung cấp, đồng bộ
  qua tài khoản Google của chính bạn giữa các máy bạn đăng nhập. Nhà phát
  triển tiện ích **không có quyền truy cập** vào dữ liệu này — nó nằm trong hạ
  tầng của Google, gắn với trình duyệt của bạn.
- **api.notion.com**: mọi ghi chú được tạo ra nằm trong **workspace Notion của
  chính bạn**, kiểm soát bởi tài khoản Notion và integration token của bạn.
  Nhà phát triển tiện ích không có quyền truy cập vào workspace đó.

Không có cơ sở dữ liệu, log server, hay bản sao lưu nào do nhà phát triển vận
hành chứa dữ liệu của bạn.

## 4. Chia sẻ với bên thứ ba

Tiện ích gọi trực tiếp REST API công khai của Notion
(`https://api.notion.com/v1/*`) bằng token do bạn cung cấp. Đây là hành động
**do bạn khởi tạo và uỷ quyền** (bạn tự tạo integration, tự chia sẻ database
với integration đó) — không phải nhà phát triển chia sẻ dữ liệu của bạn cho
Notion thay bạn.

Ngoài Notion, tiện ích **không gửi dữ liệu tới bất kỳ dịch vụ, máy chủ, hay
bên thứ ba nào khác** — không có analytics, không có crash reporting, không
có quảng cáo, không có mạng lưới theo dõi nào được nhúng.

Chúng tôi **không bán, không cho thuê, không trao đổi** dữ liệu người dùng vì
bất kỳ mục đích nào.

## 5. Quyền của bạn — xoá dữ liệu

- **Xoá dữ liệu lưu cục bộ:** gỡ cài đặt tiện ích, hoặc vào trang Cài đặt của
  tiện ích và xoá token/database đã lưu.
- **Thu hồi quyền truy cập Notion:** vào
  [notion.so/my-integrations](https://www.notion.so/my-integrations), xoá
  hoặc thu hồi integration bạn đã tạo. Sau khi thu hồi, token đã lưu trong
  tiện ích sẽ không còn hoạt động.
- **Xoá các trang đã tạo:** các trang ghi chú nằm trong workspace Notion của
  bạn — xoá trực tiếp trong Notion như mọi trang khác.

## 6. Trẻ em

Tiện ích không hướng đến trẻ em dưới 13 tuổi và không cố ý thu thập dữ liệu
từ trẻ em.

## 7. Bảo mật

Mọi kết nối tới Notion đều qua HTTPS (`Notion-Version: 2022-06-28`). Token
không bao giờ được ghi log, không bao giờ hiển thị dạng innerHTML (tránh rò
rỉ qua XSS), và chỉ được gửi tới đúng một origin: `api.notion.com`.

## 8. Thay đổi chính sách

Khi chính sách này thay đổi, ngày "Cập nhật lần cuối" ở đầu trang sẽ được cập
nhật. Bản mới nhất luôn nằm tại URL này.

## 9. Liên hệ

Câu hỏi về quyền riêng tư, vui lòng liên hệ: **thinhpq10@fpt.com**

---

## Privacy Policy — Notion Auto-Save & Note Clipper (English)

**Last updated: 2026-08-05**

This policy applies to the Chrome extension **Notion Auto-Save & Note
Clipper** (Chrome Web Store item ID: `glbhgbclpmfjlilapionmemkomhnpokp`).

### 1. Summary

- This extension has **no developer-operated backend server**.
- It does **not collect, sell, or share your data** with any third party
  other than Notion — and only when you explicitly click Save.
- No analytics, no behavioural tracking, no advertising.
- Data only ever goes to two places: your local Chrome profile (via
  `chrome.storage.sync`) and **api.notion.com**, using a Notion integration
  token that you personally create and paste in.

### 2. What data is processed

| Data | When it's read | Where it goes |
|---|---|---|
| Notion integration token (secret) | You paste it into the Options page | Stored in `chrome.storage.sync`; sent with every request to `api.notion.com` for authentication |
| Selected Notion database ID / title | After you pick or create a database | Stored in `chrome.storage.sync` |
| Text you deliberately **select/highlight** on a page | When you click Save / right-click / open the popup | Sent to `api.notion.com` to create a new page in your database |
| Title and URL of the active tab | When you click Save | Sent to `api.notion.com` as properties of the new page |
| Tags, notes, and status you type in the popup form | When you type into the form | Sent to `api.notion.com` |

The extension does **not** read page content unless you have selected text
and deliberately triggered a save. The content script only exists to render
the floating save button near your selection and a result toast — it does
not scan or copy page content in the background.

### 3. Where data is stored

- **`chrome.storage.sync`**: Google Chrome's own storage mechanism, synced
  through your Google account across your signed-in browsers. The extension
  developer has **no access** to this data — it lives in Google's
  infrastructure, tied to your browser profile.
- **api.notion.com**: every note created lives in **your own Notion
  workspace**, controlled by your Notion account and your integration token.
  The extension developer has no access to that workspace.

No database, server log, or backup operated by the developer contains your
data.

### 4. Third-party sharing

The extension calls Notion's public REST API
(`https://api.notion.com/v1/*`) directly, using the token you provide. This
is an action **you initiate and authorize** (you create the integration
yourself and connect it to your own database) — the developer is not sharing
your data with Notion on your behalf.

Other than Notion, the extension **sends data to no other service, server,
or third party** — no analytics, no crash reporting, no advertising, no
embedded tracking network of any kind.

We do **not sell, rent, or trade** user data for any purpose.

### 5. Your rights — deleting your data

- **Delete locally stored data:** uninstall the extension, or clear the
  saved token/database from the Options page.
- **Revoke Notion access:** go to
  [notion.so/my-integrations](https://www.notion.so/my-integrations) and
  delete or revoke the integration you created. Once revoked, any token
  saved in the extension stops working.
- **Delete created pages:** notes live in your own Notion workspace — delete
  them there like any other page.

### 6. Children's privacy

This extension is not directed at children under 13 and does not knowingly
collect data from children.

### 7. Security

All requests to Notion use HTTPS (`Notion-Version: 2022-06-28`). The token
is never logged, never rendered via `innerHTML` (to avoid XSS leakage), and
is only ever sent to one origin: `api.notion.com`.

### 8. Changes to this policy

When this policy changes, the "Last updated" date at the top will be
updated. The latest version always lives at this URL.

### 9. Contact

For privacy questions, contact: **thinhpq10@fpt.com**
