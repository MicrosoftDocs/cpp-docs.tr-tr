---
title: Sınıf Kitaplığına Genel Bakış
ms.date: 09/17/2019
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- grouping MFC classes
- MFC, class library
- classes [MFC], MFC
- class libraries, MFC
- class libraries
ms.assetid: 9b0e3152-ac39-4f52-91b4-f20aa3a674aa
ms.openlocfilehash: bf30f1b0aa83ef002337b76601f04c7103963441
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84620740"
---
# <a name="class-library-overview"></a>Sınıf Kitaplığına Genel Bakış

Bu genel bakış, Microsoft Foundation Class Kitaplığı (MFC) sürüm 9,0 ' de sınıfları kategorilere ayırır ve tanımlar. MFC 'deki sınıflar birlikte alınan sınıflar, bir uygulama çerçevesini oluşturur — Windows API 'si için yazılmış bir uygulamanın çatısı. Programlama göreviniz, uygulamanıza özgü kodu doldurmanızı sağlar.

Kitaplığın sınıfları aşağıdaki kategorilerde sunulmuştur:

- [Kök Sınıf: CObject](root-class-cobject.md)

- [MFC uygulama mimarisi sınıfları](mfc-application-architecture-classes.md)

  - [Uygulama ve Iş parçacığı destek sınıfları](application-and-thread-support-classes.md)

  - [Komut Yönlendirme Sınıfları](command-routing-classes.md)

  - [Belge sınıfları](document-classes.md)

  - [Görünüm Sınıfları (Mimari)](view-classes-architecture.md)

  - [Çerçeve penceresi sınıfları (mimari)](frame-window-classes-architecture.md)

  - [Belge-şablon sınıfları](document-template-classes.md)

- [Pencere, İletişim Kutusu ve Denetim Sınıfları](window-dialog-and-control-classes.md)

  - [Çerçeve penceresi sınıfları (Windows)](frame-window-classes-windows.md)

  - [Görünüm sınıfları (Windows)](view-classes-windows.md)

  - [İletişim kutusu sınıfları](dialog-box-classes.md)

  - [Denetim sınıfları](control-classes.md)

  - [Denetim çubuğu sınıfları](control-bar-classes.md)

- [Sınıf Çizme ve Boyama](drawing-and-printing-classes.md)

  - [Çıktı (Cihaz Bağlamı) Sınıfları](output-device-context-classes.md)

  - [Çizim aracı sınıfları](drawing-tool-classes.md)

- [Basit Veri Türü Sınıfları](simple-data-type-classes.md)

- [Dizi, liste ve eşleme sınıfları](array-list-and-map-classes.md)

  - [Diziler, listeler ve haritalar için şablon sınıfları](template-classes-for-arrays-lists-and-maps.md)

  - [Kullanıma Hazır Dizi Sınıfları](ready-to-use-array-classes.md)

  - [Kullanıma Hazır Liste Sınıfları](ready-to-use-list-classes.md)

  - [Kullanıma hazırlama eşleme sınıfları](ready-to-use-map-classes.md)

- [Dosya ve Veritabanı Sınıfları](file-and-database-classes.md)

  - [Dosya g/ç sınıfları](file-i-o-classes.md)

  - [DAO Sınıfları](dao-classes.md)

  - [ODBC Sınıfları](odbc-classes.md)

  - [OLE DB sınıfları](ole-db-classes.md)

- [Internet ve ağ sınıfları](internet-and-networking-classes.md)

  - [Windows Sockets sınıfları](windows-sockets-classes.md)

  - [Win32 Internet Sınıfları](win32-internet-classes.md)

- [OLE Sınıfları](ole-classes.md)

  - [OLE kapsayıcı sınıfları](ole-container-classes.md)

  - [OLE sunucu sınıfları](ole-server-classes.md)

  - [OLE sürükle ve bırak ve Veri Aktarımı sınıfları](ole-drag-and-drop-and-data-transfer-classes.md)

  - [OLE Ortak İletişim Kutusu Sınıfları](ole-common-dialog-classes.md)

  - [OLE Otomasyon Sınıfları](ole-automation-classes.md)

  - [OLE Denetim Sınıfları](ole-control-classes.md)

  - [Etkin Belge Sınıfları](active-document-classes.md)

  - [OLE ile Ilgili sınıflar](ole-related-classes.md)

- [Hata Ayıklama ve Özel Durum Sınıfları](debugging-and-exception-classes.md)

  - [Destek sınıflarında hata ayıklama](debugging-support-classes.md)

  - [Özel durum sınıfları](exception-classes.md)

[Genel sınıf tasarımı felsefesi](general-class-design-philosophy.md) , MFC kitaplığının nasıl tasarlandığını açıklar.

Çerçeveye genel bakış için bkz. [Windows Için uygulama yazmak Için sınıfları kullanma](using-the-classes-to-write-applications-for-windows.md). Yukarıda listelenen sınıfların bazıları, çerçeve dışında kullanılabilecek genel amaçlı sınıflardır ve koleksiyonlar, özel durumlar, dosyalar ve dizeler gibi yararlı soyutlamalar sağlar.

Bir sınıfın devralınmasını görmek için [sınıf hiyerarşisi grafiğini](hierarchy-chart.md)kullanın.

Bu genel bakışta listelenen sınıflara ek olarak, MFC kitaplığı bir dizi genel işlevler, genel değişkenler ve makrolar içerir. MFC [makroları ve](reference/mfc-macros-and-globals.md)genel konu başlığında MFC sınıflarına ilişkin alfabetik başvuruyu izleyen genel bakış ve ayrıntılı bir liste vardır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC masaüstü uygulamaları](mfc-desktop-applications.md)
