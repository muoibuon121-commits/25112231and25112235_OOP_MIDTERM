# Muoi — Documentation

Ứng dụng native macOS quản lý hóa đơn B2B, xây dựng bằng SwiftUI + Core Data.

## Tính năng

### Quản lý hóa đơn
- Tạo, chỉnh sửa, xóa hóa đơn
- Tính tự động VAT (0/5/8/10%) và chiết khấu
- Theo dõi trạng thái thanh toán, cảnh báo quá hạn
- Sinh VietQR chuyển khoản theo số hóa đơn
- Hỗ trợ đa tiền tệ với tỷ giá thời gian thực

### Quản lý khách hàng
- CRUD đầy đủ: công ty, liên hệ, mã số thuế, địa chỉ
- Hạn mức tín dụng, kỳ thanh toán, trạng thái
- Thống kê doanh thu theo khách hàng
- Chọn quốc gia từ danh sách thế giới

### Dashboard
- Tổng doanh thu, công nợ, số hóa đơn quá hạn
- Hóa đơn gần đây
- Tỷ giá ngoại tệ cập nhật trong ngày

### Tùy chọn
- Giao diện sáng/tối (thích ứng Asset Catalog)
- Ngôn ngữ: Tiếng Việt / Tiếng Anh
- VAT & chiết khấu mặc định
- Cấu hình ngân hàng & VietQR (bank ID, số tài khoản, tên TK)
- Đồng bộ tự động

## Yêu cầu

|  |  |
| --- | --- |
| macOS | 13.0+ |
| Xcode | 15.0+ |
| Swift | 5.9+ |

## Cấu trúc mã nguồn

```
App/
  B2BApp.swift              @main + AppDelegate + menu bar
  Assets.xcassets           Màu thích ứng light/dark + icon
Models/
  Models.swift              Invoice, Client Core Data entities
Services/
  CoreDataManager.swift     Core Data stack, CRUD
  SyncManager.swift         Auto-sync
  APIService.swift          Tỷ giá, quốc gia, VietQR URL
Utilities/
  Constants.swift           AppConstants: cấu hình toàn app
  Extensions.swift          Màu, modifier glass, formatter
  Localization.swift        LocalizationManager (vi/en)
  ValidationHelper.swift    Validate email, phone, amount…
Views/
  MainWindow.swift          NavigationSplitView shell
  MainSidebar.swift         Sidebar menu
  DashboardView.swift       StatCard.swift
  InvoiceListView.swift     InvoiceTableView.swift
  InvoiceDetailView.swift   NewInvoiceSheet.swift
  ClientsListView.swift     ClientsTableView.swift
  NewClientSheet.swift
  SettingsView.swift        SettingsFormView.swift
  PreferencesWindow.swift   AboutWindow.swift
  ListHeaderToolbar.swift
```

## Build & Run

```
# Mở trong Xcode
open B2BInvoiceApp.xcodeproj

# Hoặc build trực tiếp
xcodebuild -project B2BInvoiceApp.xcodeproj \
           -scheme B2BInvoiceApp \
           -configuration Release build
```

Binary xuất ra tại `~/Library/Developer/Xcode/DerivedData/B2BInvoiceApp-*/Build/Products/Release/Muoi.app`.

## Phím tắt

| Phím | Tác vụ |
| --- | --- |
| Cmd+N | Tạo hóa đơn mới |
| Cmd+Shift+C | Tạo khách hàng mới |
| Cmd+, | Mở Tùy chọn |
| Cmd+Q | Thoát |

## Tùy biến

- **Màu sắc / giao diện**: sửa Asset Catalog `App/Assets.xcassets/Colors` — mỗi màu có variant Light/Dark
- **Màu nhấn (pink)**: sửa `Color.appIndigo/appBlue/appViolet` trong `Utilities/Extensions.swift`
- **Ngân hàng & tiền tệ mặc định**: `Utilities/Constants.swift` → `AppConstants.Currencies` / `AppConstants.Finance`
- **Thêm chuỗi dịch**: bổ sung key vào `Utilities/Localization.swift` → `viToEn`
- **Menu & phím tắt**: `App/B2BApp.swift`

## Xử lý sự cố

**Build lỗi sau khi kéo file mới**
Kiểm tra target membership của file `.swift`; Clean Build Folder (Cmd+Shift+K) rồi build lại.

**Crash Core Data sau khi đổi schema**
Xóa app và dữ liệu cục bộ, build lại:
```
rm -rf ~/Library/Containers/com.muoi.B2BInvoiceApp
```

**Giao diện không đổi khi chuyển sáng/tối**
Không hardcode `.preferredColorScheme` ở WindowGroup; appearance được đọc từ `UserDefaults("appearanceMode")` trong `AppDelegate`.

## License

MIT © Muoi
