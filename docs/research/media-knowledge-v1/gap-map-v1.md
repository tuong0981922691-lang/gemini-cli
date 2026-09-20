# Bản đồ khoảng trống tri thức v1

## 1. Phạm vi và nguyên tắc bằng chứng

Tài liệu này là kết quả **Giai đoạn 1**, ngày truy cập `2026-09-20` (UTC). Một
khẳng định chỉ được coi là đã xác minh khi có nguồn chính thức, định danh phiên
bản/commit, thời điểm truy cập và bằng chứng ở cấp tệp hoặc đoạn. URL do người
dùng cung cấp chỉ là manh mối nguồn, không tự động là bằng chứng về nội dung.

Không tìm thấy tệp **“BÁO CÁO KIỂM ĐỊNH TRI THỨC.docx”** trong workspace. Vì vậy
không có kết luận nào của báo cáo được nâng trạng thái thành đã xác minh, bị
loại bỏ, hay được giữ nguyên. Đây là khoảng trống chặn việc đối chiếu báo cáo,
không phải bằng chứng rằng báo cáo không tồn tại.

## 2. Sổ trạng thái ban đầu

| Nhóm                 | Trạng thái                                                                                 | Căn cứ hiện có                                           | Hành động tiếp theo                                                |
| -------------------- | ------------------------------------------------------------------------------------------ | -------------------------------------------------------- | ------------------------------------------------------------------ |
| Nội dung đã xác minh | Trống                                                                                      | Chưa có đoạn nguồn có phiên bản                          | Thu thập nguồn chính thức ở Giai đoạn 2                            |
| Vùng cách ly         | Các MCP candidate GLIF, CometChat và OpusClip; mọi khẳng định chưa đối chiếu trong báo cáo | URL/owner do người dùng cung cấp; truy cập mạng thất bại | Cấp snapshot hoặc mở truy cập chỉ đọc, sau đó băm và kiểm tra tĩnh |
| Nội dung bị loại bỏ  | Trống                                                                                      | Chưa đủ bằng chứng để loại bỏ                            | Chỉ ghi `LOAI_BO` kèm lý do và bằng chứng                          |
| Khoảng trống         | Báo cáo DOCX; metadata GLIF; toàn bộ ma trận miền                                          | Artifact/nguồn chưa khả dụng                             | Thu thập theo kế hoạch khảo sát                                    |
| Cần tái kiểm định    | Chưa xác định                                                                              | Chưa có baseline phiên bản                               | Đặt ngày tái kiểm định theo độ biến động                           |

## 3. Bản đồ khoảng trống theo miền

Thang ưu tiên: **P0** chặn quyết định an toàn/pháp lý; **P1** chặn kiến trúc;
**P2** tối ưu hóa hoặc mở rộng.

| Miền                | Đã có                           | Khoảng trống cần chứng minh                                                                    | Ưu tiên | Bằng chứng tối thiểu                                                              |
| ------------------- | ------------------------------- | ---------------------------------------------------------------------------------------------- | ------- | --------------------------------------------------------------------------------- |
| Video/codec         | Taxonomy yêu cầu                | Khả năng demux–package, màu/HDR, CFR/VFR, chất lượng; giấy phép phần mềm tách khỏi patent pool | P0      | Spec, LICENSE, build flags, test vectors, patent/licensing authority              |
| Hình ảnh            | Taxonomy yêu cầu                | Provenance C2PA, ICC/EXIF, chất lượng matting/OCR/restoration, tính nhất quán                  | P1      | Spec, model card, benchmark có dữ liệu/phương pháp                                |
| Âm thanh/lời thoại  | Taxonomy yêu cầu                | WER/DER, alignment, loudness, ngôn ngữ; quyền giọng nói và dữ liệu                             | P0      | Model/data license, benchmark, privacy/consent policy                             |
| AI tạo/hiểu video   | Taxonomy yêu cầu                | License code/weight/data, VRAM/độ trễ/độ dài, temporal consistency, readiness                  | P0      | Model card, release SHA, benchmark tái lập, safety policy                         |
| Agent/MCP/plugin    | Ứng viên GLIF do người dùng nêu | Owner, HEAD, API/tool boundary, auth, side effects, telemetry, failure recovery                | P0      | Snapshot bất biến, manifest, security policy, threat model, static tool inventory |
| Kho tri thức        | Schema v1                       | Ontology, chunking, retrieval, benchmark, dedup/quarantine/revalidation workflow               | P1      | Versioned schema, gold set, provenance tests                                      |
| Máy tính/hạ tầng    | Taxonomy yêu cầu                | Ma trận Windows/runtime/EP/GPU-NPU, driver, memory, fallback CPU                               | P1      | Vendor docs theo version, reproducible benchmark protocol                         |
| Pháp lý/bảo mật     | Quy tắc tách loại giấy phép     | Transitive dependencies, patents, SBOM, secrets, advisories, distribution duties               | P0      | License texts, lockfiles, SBOM, official advisory databases                       |
| Vận hành/thương mại | Chưa có                         | SLO, cost, support, observability, offline/cloud policy, buy/build/integrate                   | P1      | Pricing/SLA chính thức có ngày, load/failure tests                                |
| Báo cáo gốc         | Chỉ có tên do người dùng nêu    | Toàn bộ nội dung, phiên bản, tác giả, hash                                                     | P0      | DOCX gốc + SHA-256 + thời điểm tiếp nhận                                          |

## 4. Câu hỏi quyết định bắt buộc

1. **Nguồn gốc:** chủ sở hữu và URL canonical có được chứng minh bằng metadata
   chính thức không?
2. **Tính bất biến:** SHA commit/release và hash artifact có đủ để tái lập
   không?
3. **Quyền sử dụng:** license code, weight, training data, plugin và dependency
   đã được tách riêng chưa?
4. **An toàn:** thành phần có network, credential, filesystem, subprocess hay
   side effect nào; approval boundary ở đâu?
5. **Khả năng:** chất lượng, latency, memory, hardware và failure mode đã được
   đo trên workload chuẩn chưa?
6. **Vận hành:** bảo trì, security response, telemetry, offline degradation, chi
   phí và lock-in có chấp nhận được không?

## 5. Bộ đầu ra và gate

| Đầu ra bắt buộc                                    | Giai đoạn tạo baseline | Gate chấp nhận                                       |
| -------------------------------------------------- | ---------------------- | ---------------------------------------------------- |
| Bản đồ năng lực, taxonomy, danh mục nguồn/ứng viên | 1                      | Có owner/source class và khoảng trống rõ ràng        |
| Knowledge Registry, quarantine/blacklist           | 1–2                    | Schema hợp lệ; mọi claim có evidence ref             |
| Ma trận công nghệ, phần cứng, license/patent       | 2–3                    | Không trộn license; số đo có protocol/version        |
| Cây dependency/plugin và risk register             | 3                      | Lockfile/SBOM, advisory snapshot, control owner      |
| Benchmark/evaluation cố định                       | 2–4                    | Dataset hợp pháp, metric/pass threshold, seed/config |
| Kiến trúc local/hybrid/cloud; build/buy/integrate  | 5–6                    | Chỉ dùng mục `TINH_HOA`/`DAT`; có phương án hạ cấp   |
| Lộ trình thi công                                  | 6                      | Mỗi mốc có owner, evidence, rollback và gate         |

## 6. Mức tin cậy hiện tại

- **Cao:** chỉ với quan sát cục bộ rằng DOCX và snapshot không có trong
  workspace tại thời điểm kiểm tra.
- **Thấp:** URL và owner GLIF mới là dữ liệu do người dùng cung cấp, chưa được
  đối chiếu với GitHub.
- **Không đánh giá:** nhánh mặc định, SHA, ngày commit, release, license,
  dependency, maintenance và security của GLIF. Không được suy đoán các trường
  này.

Ngày tái kiểm định đề xuất cho bản đồ: `2026-10-20`, hoặc ngay khi nhận DOCX và
snapshot bất biến (điều kiện nào đến trước).
