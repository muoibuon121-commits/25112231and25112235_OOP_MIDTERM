<p align="center">
  <img width="121" height="121" alt="icon" src="https://github.com/user-attachments/assets/04d8b894-6003-4821-94a5-e82281134789" />

</p>

# Check this OUT ! Tải ngay .dmg trên web mà không cần clone repo !
<p align="center">
https://25112231and25112235oopmidterm.vercel.app

</p>


# Muoi — B2B Invoice Manager

Ứng dụng native macOS quản lý hóa đơn B2B: tạo hóa đơn, quản lý khách hàng, theo dõi doanh thu, xuất VietQR thanh toán. Giao diện SwiftUI với hỗ trợ sáng/tối và song ngữ Việt/Anh.

  ![Swift](https://img.shields.io/badge/Language-Swift%205.9-F05138?style=flat&logo=swift&logoColor=white)
  ![SwiftUI](https://img.shields.io/badge/UI-SwiftUI-0070C9?style=flat&logo=apple&logoColor=white)                                                                                                        
  ![CoreData](https://img.shields.io/badge/Database-CoreData%20%2B%20SQLite-003B57?style=flat&logo=sqlite&logoColor=white)                                                                                
  ![macOS](https://img.shields.io/badge/Platform-macOS%2013%2B-000000?style=flat&logo=apple&logoColor=white)                                                                                              
  ![Xcode](https://img.shields.io/badge/IDE-Xcode%2015-147EFB?style=flat&logo=xcode&logoColor=white) ![VietQR](https://img.shields.io/badge/API-VietQR-E31837?style=flat&logo=qrcode&logoColor=white)   
  ![Architecture](https://img.shields.io/badge/Architecture-MVVM-6DB33F?style=flat&logo=diagram&logoColor=white)
  ![License](https://img.shields.io/badge/License-MIT-green?style=flat&logo=opensourceinitiative&logoColor=white)

## Tính năng
```
- Hóa đơn: tạo, chỉnh sửa, theo dõi thanh toán, cảnh báo quá hạn, VAT & chiết khấu tự động
- Khách hàng: CRUD, hạn mức tín dụng, thống kê doanh thu
- Dashboard: tổng quan doanh thu, công nợ, hóa đơn quá hạn, tỷ giá ngoại tệ
- VietQR: sinh mã QR chuyển khoản theo số hóa đơn
- Đa ngôn ngữ: Tiếng Việt / Tiếng Anh
- Giao diện: sáng/tối thích ứng, Liquid Glass
```

## Yêu cầu
```
- macOS 13.0+
- Xcode 15+
- Swift 5.9+
```
## Chạy dự án

```bash
open B2BInvoiceApp.xcodeproj
# Product → Run (Cmd+R)
```

Hoặc build release:

```bash
xcodebuild -project B2BInvoiceApp.xcodeproj -scheme B2BInvoiceApp -configuration Release build
```

## Cấu trúc

```
App/          Entry point + Assets
Models/       Core Data entities (Invoice, Client)
Services/     CoreDataManager, SyncManager, APIService
Utilities/    Constants, Extensions, Localization, ValidationHelper
Views/        SwiftUI views (dashboard, list, detail, sheet, settings)
Documentation/Tài liệu chi tiết
website/      Landing page & file .dmg phân phối
```

Chi tiết tài liệu tham khảo [Documentation/README.md](Documentation/README.md).

## License

MIT © Muoi
