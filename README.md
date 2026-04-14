<p align="center">

  <img width="121" height="121" alt="icon" src="https://github.com/user-attachments/assets/04d8b894-6003-4821-94a5-e82281134789" />

</p>



<h1 align="center">Muoi — B2B Invoice Manager</h1>



<p align="center">

  Ứng dụng native macOS quản lý hóa đơn B2B: tạo hóa đơn, quản lý khách hàng, theo dõi doanh thu, xuất VietQR thanh toán.<br/>

  Giao diện SwiftUI với hỗ trợ sáng/tối và song ngữ Việt/Anh.

</p>



<p align="center">

  <b>Tải ngay .dmg:</b> <a href="https://25112231and25112235oopmidterm.vercel.app">25112231and25112235oopmidterm.vercel.app</a>

</p>



<p align="center">

  <img src="https://img.shields.io/badge/Language-Swift%205.9-F05138?style=flat" />

  <img src="https://img.shields.io/badge/UI-SwiftUI-0070C9?style=flat" />

  <img src="https://img.shields.io/badge/Database-CoreData%20%2B%20SQLite-003B57?style=flat" />

  <img src="https://img.shields.io/badge/Platform-macOS%2013%2B-000000?style=flat" />

  <img src="https://img.shields.io/badge/IDE-Xcode%2015-147EFB?style=flat" />

  <img src="https://img.shields.io/badge/API-VietQR-E31837?style=flat" />

  <img src="https://img.shields.io/badge/Architecture-MVVM-6DB33F?style=flat" />

  <img src="https://img.shields.io/badge/License-MIT-green?style=flat" />

</p>







Mục lục







Giới thiệu



Tính năng



Quản lý hóa đơn



Quản lý khách hàng



Dashboard



Tùy chọn



Yêu cầu hệ thống



Chạy dự án



Cấu trúc mã nguồn



Phím tắt



Tùy biến



Xử lý sự cố



License







Giới thiệu



Muoi là ứng dụng native macOS xây dựng bằng SwiftUI và Core Data, phục vụ doanh nghiệp B2B quản lý toàn bộ quy trình hóa đơn từ tạo lập đến theo dõi thanh toán. Ứng dụng hỗ trợ đa ngôn ngữ Việt/Anh, giao diện sáng/tối thích ứng, và tích hợp VietQR để tạo mã chuyển khoản trực tiếp từ hóa đơn.







Tính năng



Quản lý hóa đơn







Tạo, chỉnh sửa, xóa hóa đơn



Tính tự động VAT (0/5/8/10%) và chiết khấu



Theo dõi trạng thái thanh toán, cảnh báo quá hạn



Sinh VietQR chuyển khoản theo số hóa đơn



Hỗ trợ đa tiền tệ với tỷ giá thời gian thực



Quản lý khách hàng







CRUD đầy đủ: công ty, liên hệ, mã số thuế, địa chỉ



Hạn mức tín dụng, kỳ thanh toán, trạng thái



Thống kê doanh thu theo khách hàng



Chọn quốc gia từ danh sách thế giới



Dashboard







Tổng doanh thu, công nợ, số hóa đơn quá hạn



Danh sách hóa đơn gần đây



Tỷ giá ngoại tệ cập nhật trong ngày



Tùy chọn







Giao diện sáng/tối (thích ứng Asset Catalog)



Ngôn ngữ: Tiếng Việt / Tiếng Anh



VAT và chiết khấu mặc định



Cấu hình ngân hàng và VietQR (bank ID, số tài khoản, tên tài khoản)



Đồng bộ tự động







Yêu cầu hệ thống









Thành phần



Phiên bản





macOS



13.0+





Xcode



15.0+





Swift



5.9+







Chạy dự án



Mở project trong Xcode và chạy:



open B2BInvoiceApp.xcodeproj
# Product → Run (Cmd+R)



Hoặc build release từ dòng lệnh:



xcodebuild -project B2BInvoiceApp.xcodeproj \
           -scheme B2BInvoiceApp \
           -configuration Release build



Binary xuất ra tại:



~/Library/Developer/Xcode/DerivedData/B2BInvoiceApp-*/Build/Products/Release/Muoi.app







Cấu trúc mã nguồn



App/
  B2BApp.swift              Entry point + AppDelegate + menu bar
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
  ValidationHelper.swift    Validate email, phone, amount
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
Documentation/              Tài liệu chi tiết
website/                    Landing page và file .dmg phân phối



Chi tiết tham khảo [Documentation/README.md](</Users/muoi/Downloads/Documentation/README.md>).







Phím tắt









Phím



Tác vụ





Cmd+N



Tạo hóa đơn mới





Cmd+Shift+C



Tạo khách hàng mới





Cmd+,



Mở Tùy chọn





Cmd+Q



Thoát







Tùy biến







Màu sắc và giao diện: sửa Asset Catalog App/Assets.xcassets/Colors, mỗi màu có variant Light/Dark



Màu nhấn: sửa Color.appIndigo/appBlue/appViolet trong Utilities/Extensions.swift



Ngân hàng và tiền tệ mặc định: Utilities/Constants.swift → AppConstants.Currencies và AppConstants.Finance



Thêm chuỗi dịch: bổ sung key vào Utilities/Localization.swift → viToEn



Menu và phím tắt: App/B2BApp.swift







Xử lý sự cố



Build lỗi sau khi kéo file mới

Kiểm tra target membership của file .swift, Clean Build Folder (Cmd+Shift+K) rồi build lại.



Crash Core Data sau khi đổi schema

Xóa app và dữ liệu cục bộ, build lại:



rm -rf ~/Library/Containers/com.muoi.B2BInvoiceApp



Giao diện không đổi khi chuyển sáng/tối

Không hardcode .preferredColorScheme ở WindowGroup. Appearance được đọc từ UserDefaults("appearanceMode") trong AppDelegate.







License



MIT © Muoi

