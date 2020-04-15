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
ms.openlocfilehash: 9b307c4993a1a7a397741864381c0739a1f4c4ea
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81374586"
---
# <a name="class-library-overview"></a>Sınıf Kitaplığına Genel Bakış

Bu genel bakış, Microsoft Hazırlık Sınıf Kitaplığı (MFC) sürüm 9.0'daki sınıfları kategorilere ayırır ve açıklar. MFC'deki sınıflar, birlikte alınan, Windows API için yazılmış bir uygulamanın çerçevesi olan bir uygulama çerçevesi oluşturur. Programlama göreviniz, uygulamanıza özgü kodu doldurmaktır.

Kütüphanenin sınıfları burada aşağıdaki kategorilerde sunulmuştur:

- [Kök Sınıf: CObject](../mfc/root-class-cobject.md)

- [MFC Uygulama Mimarisi Sınıfları](../mfc/mfc-application-architecture-classes.md)

  - [Uygulama ve Konu Destek Sınıfları](../mfc/application-and-thread-support-classes.md)

  - [Komut Yönlendirme Sınıfları](../mfc/command-routing-classes.md)

  - [Belge Sınıfları](../mfc/document-classes.md)

  - [Görünüm Sınıfları (Mimari)](../mfc/view-classes-architecture.md)

  - [Çerçeve Penceresi Sınıfları (Mimari)](../mfc/frame-window-classes-architecture.md)

  - [Belge Şablonu Sınıfları](../mfc/document-template-classes.md)

- [Pencere, İletişim Kutusu ve Denetim Sınıfları](../mfc/window-dialog-and-control-classes.md)

  - [Çerçeve Penceresi Sınıfları (Windows)](../mfc/frame-window-classes-windows.md)

  - [Sınıfları Görüntüle (Windows)](../mfc/view-classes-windows.md)

  - [İletişim Kutusu Sınıfları](../mfc/dialog-box-classes.md)

  - [Kontrol Sınıfları](../mfc/control-classes.md)

  - [Kontrol Çubuğu Sınıfları](../mfc/control-bar-classes.md)

- [Sınıf Çizme ve Boyama](../mfc/drawing-and-printing-classes.md)

  - [Çıktı (Cihaz Bağlamı) Sınıfları](../mfc/output-device-context-classes.md)

  - [Çizim Aracı Sınıfları](../mfc/drawing-tool-classes.md)

- [Basit Veri Türü Sınıfları](../mfc/simple-data-type-classes.md)

- [Dizi, Liste ve Harita Sınıfları](../mfc/array-list-and-map-classes.md)

  - [Diziler, Listeler ve Haritalar için Şablon Sınıfları](../mfc/template-classes-for-arrays-lists-and-maps.md)

  - [Kullanıma Hazır Dizi Sınıfları](../mfc/ready-to-use-array-classes.md)

  - [Kullanıma Hazır Liste Sınıfları](../mfc/ready-to-use-list-classes.md)

  - [Kullanıma Hazır Harita Sınıfları](../mfc/ready-to-use-map-classes.md)

- [Dosya ve Veritabanı Sınıfları](../mfc/file-and-database-classes.md)

  - [Dosya G/Ç Sınıfları](../mfc/file-i-o-classes.md)

  - [DAO Sınıfları](../mfc/dao-classes.md)

  - [ODBC Sınıfları](../mfc/odbc-classes.md)

  - [OLE DB Sınıfları](../mfc/ole-db-classes.md)

- [İnternet ve Ağ Sınıfları](../mfc/internet-and-networking-classes.md)

  - [Windows Soketleri Sınıfları](../mfc/windows-sockets-classes.md)

  - [Win32 Internet Sınıfları](../mfc/win32-internet-classes.md)

- [OLE Sınıfları](../mfc/ole-classes.md)

  - [OLE Konteyner Sınıfları](../mfc/ole-container-classes.md)

  - [OLE Sunucu Sınıfları](../mfc/ole-server-classes.md)

  - [OLE Sürükle ve Bırak ve Veri Aktarım Sınıfları](../mfc/ole-drag-and-drop-and-data-transfer-classes.md)

  - [OLE Ortak İletişim Kutusu Sınıfları](../mfc/ole-common-dialog-classes.md)

  - [OLE Otomasyon Sınıfları](../mfc/ole-automation-classes.md)

  - [OLE Denetim Sınıfları](../mfc/ole-control-classes.md)

  - [Etkin Belge Sınıfları](../mfc/active-document-classes.md)

  - [OLE Ile İlgili Sınıflar](../mfc/ole-related-classes.md)

- [Hata Ayıklama ve Özel Durum Sınıfları](../mfc/debugging-and-exception-classes.md)

  - [Hata Ayıklama Destek Sınıfları](../mfc/debugging-support-classes.md)

  - [Özel Durum Sınıfları](../mfc/exception-classes.md)

Genel [Sınıf Tasarım Felsefesi](../mfc/general-class-design-philosophy.md) bölümü, MFC Kitaplığı'nın nasıl tasarlandığını açıklar.

Çerçeveye genel bir bakış için windows [için uygulama yazmak için Sınıfları Kullanma bölümüne](../mfc/using-the-classes-to-write-applications-for-windows.md)bakın. Yukarıda listelenen sınıflardan bazıları, çerçevenin dışında kullanılabilen ve koleksiyonlar, özel durumlar, dosyalar ve dizeleri gibi yararlı soyutlamalar sağlayan genel amaçlı sınıflardır.

Bir sınıfın kalıtımını görmek için [Sınıf Hiyerarşisi Grafiği'ni](../mfc/hierarchy-chart.md)kullanın.

Bu genel bakışta listelenen sınıflara ek olarak, MFC Kitaplığı bir dizi genel işlev, genel değişken ve makro içerir. MFC sınıflarına alfabetik başvuruyu izleyen [MFC Makroları ve Globaller (MFC Makroları ve Globalleri)](../mfc/reference/mfc-macros-and-globals.md)konusunda bunların genel ve ayrıntılı bir listesi vardır.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Masaüstü Uygulamaları](../mfc/mfc-desktop-applications.md)
