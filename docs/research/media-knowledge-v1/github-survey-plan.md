# Kế hoạch khảo sát GitHub theo từng miền

## 1. Quy trình thu thập an toàn

### Gate A — nhận diện nguồn (Giai đoạn 1)

1. Tìm ứng viên từ spec/vendor/paper chính thức; không dùng stars làm tiêu chí.
2. Xác minh liên kết từ trang chủ tổ chức tới repository và owner canonical.
3. Ghi URL, owner, visibility, archived/fork state và nhánh mặc định, kèm ngày
   truy cập. Fork hoặc repo đồng danh vào `CAN_XAC_MINH`.

### Gate B — snapshot và metadata (Giai đoạn 2)

1. Tạo mirror Git riêng, không checkout và không dùng recursive submodule:
   `git clone --mirror --no-local <canonical-url> <isolated-path>.git`.
2. Ghi SHA đầy đủ của commit được chọn; author/committer timestamp; ref/tag;
   object format; remote URL; thời điểm UTC; tool version; và SHA-256 của bundle
   hoặc danh sách object/ref. Giữ lịch sử đầy đủ nếu chính sách dung lượng cho
   phép.
3. Gỡ mọi quyền ghi sau khi xác minh object bằng `git fsck --full`; không thêm
   snapshot vào dependency graph hay executable path.
4. Nếu chỉ nhận archive không có `.git`, bắt buộc có source manifest được ký
   hoặc kiểm soát phiên bản, SHA commit từ API chính thức, SHA-256 archive, danh
   sách file/hash và thời điểm thu thập. Archive không đủ metadata vẫn cách ly.

### Gate C — kiểm tra tĩnh (Giai đoạn 2–3)

Chỉ đọc qua Git object database: `README*`, `LICENSE*`, `NOTICE*`, `COPYING*`,
`SECURITY*`, `CHANGELOG*`, `CITATION*`, `CODEOWNERS`, manifest, lockfile,
container manifest và workflow. Không checkout executable, không cài package,
không tải release asset, binary, LFS object, model hoặc dataset; không chạy
hook, build, test, lifecycle script hay MCP server.

Lập inventory tool/capability, entry point, network/credential/filesystem/
subprocess access bằng phân tích văn bản. Mọi kết luận hành vi vẫn là
`CAN_XAC_MINH` cho tới khi có code review và test được phê duyệt.

### Gate D — kiểm định và thử nghiệm (Giai đoạn 3–4)

- Dựng cây dependency trực tiếp/bắc cầu từ manifest + lockfile, đối chiếu
  license text và advisory chính thức; tạo SBOM nhưng không resolve/install
  package.
- Threat-model, secret scan và static analysis trong môi trường không thực thi
  code của ứng viên.
- Chỉ sau phê duyệt bằng văn bản mới tạo sandbox cô lập, pin SHA/hash, chặn
  secret và egress mặc định, đặt resource/cost limit rồi chạy test tối thiểu.

## 2. Ma trận khảo sát theo miền

| Miền             | Tệp/bằng chứng ưu tiên                                       | Metadata/claim cần trích                              | Kiểm định kế tiếp                            |
| ---------------- | ------------------------------------------------------------ | ----------------------------------------------------- | -------------------------------------------- |
| Video/codec      | LICENSE, configure/build docs, codec/filter docs, changelog  | container/codec/filter, platform, HW backend, flags   | patent review, conformance và quality corpus |
| Image            | model card, LICENSE, data docs, inference manifest           | task, format/color metadata, weight/data terms        | quality/provenance benchmark                 |
| Audio/speech     | model/data cards, language list, benchmark                   | task/language, WER/DER, consent constraints           | fixed multilingual/noise corpus              |
| Video AI         | model/release cards, config, weight links                    | max duration/resolution, VRAM, control, safety        | temporal/identity/performance suite          |
| Agent/MCP        | README, protocol manifest, package/lock, SECURITY, workflows | tools/resources/prompts, permissions, transport, auth | threat model then sandbox approval           |
| Knowledge/RAG    | schema/index docs, benchmark/eval manifests                  | store/retrieval/reranker, provenance granularity      | frozen gold set and retrieval metrics        |
| Runtime/hardware | support matrix, release notes, driver/provider docs          | OS/device/driver/runtime compatibility                | controlled tier matrix benchmark             |
| Legal/security   | exact license/notice, SBOM/lockfile, policy/advisory         | obligations, patents, CVEs, disclosure SLA            | counsel/security owner sign-off              |

## 3. Quy tắc chấm nguồn và nhãn

Chấm mỗi chiều 0–5 với rationale và evidence ID: accuracy, verifiability,
completeness, freshness, applicability và source reliability. Không tổng hợp
điểm nếu trường P0 còn `unknown`. Nhãn:

- `TINH_HOA`: nguồn chính thức, bất biến, bằng chứng đủ và các gate P0 đạt.
- `DAT`: dùng được trong phạm vi ghi rõ nhưng không làm mỏ neo.
- `CAN_XAC_MINH`: thiếu provenance/version/license/security hoặc có mâu thuẫn.
- `LOAI_BO`: sai nguồn, không thể truy nguyên, vi phạm policy hoặc rủi ro không
  thể giảm; luôn lưu lý do, bằng chứng và người quyết định.

## 4. Lịch tái kiểm định

- Security/advisory và dịch vụ cloud: 30 ngày hoặc khi có cảnh báo.
- Active software/model: 90 ngày hoặc khi có release/default-branch change.
- Standard, patent/license hoặc archived project: 180 ngày; sớm hơn khi có thay
  đổi pháp lý.
- Mỗi lần tái kiểm định tạo revision mới; không ghi đè evidence cũ.

## 5. Trạng thái ứng viên GLIF

Canonical URL được yêu cầu: `https://github.com/glifxyz/glif-mcp-server`; owner
dự kiến: `glifxyz`. Ngày thử truy cập: `2026-09-20` UTC. Kết nối tới GitHub qua
`git`, GitHub API và raw content đều bị proxy trả HTTP 403, vì vậy **không có
snapshot**, và nhánh mặc định, SHA, ngày commit, license, release, maintenance,
security và dependency đều là `unknown`. Chi tiết máy đọc được nằm trong source
record; nhãn là `CAN_XAC_MINH`, độ tin cậy nguồn hiện tại thấp.

Để gỡ chặn: cung cấp mirror/bundle Git tin cậy có refs và history, hoặc cho phép
truy cập chỉ đọc tới repository/API chính thức. Sau đó thực hiện Gate B–C; vẫn
không chạy bất kỳ mã nào trước khi Giai đoạn 4 được phê duyệt.
