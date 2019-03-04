---
title: Sınıf Kitaplığına Genel Bakış
ms.date: 11/04/2016
f1_keywords:
- vc.classes.mfc
helpviewer_keywords:
- grouping MFC classes
- MFC, class library
- classes [MFC], MFC
- class libraries, MFC
- class libraries
ms.assetid: 9b0e3152-ac39-4f52-91b4-f20aa3a674aa
ms.openlocfilehash: aec295ea93868ff1fe6e0d3d1d2370a344e47c73
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57278775"
---
# <a name="class-library-overview"></a>Sınıf Kitaplığına Genel Bakış

Bu genel bakışta, kategorilere ayırır ve sınıflar, Microsoft Foundation Class Kitaplığı (MFC) sürüm 9.0 açıklanmaktadır. Bir uygulama çerçevesi birlikte MFC'deki sınıflar oluşturur — Windows API için yazılan uygulamanın çerçevesi. Programlama göreviniz, uygulamanıza özgü kodu doldurmak için var.

Burada Kitaplık sınıfları aşağıdaki kategorilerde sunulan:

- [Kök sınıf: CObject](../mfc/root-class-cobject.md)

- [MFC Uygulama Mimarisi Sınıfları](../mfc/mfc-application-architecture-classes.md)

   - [Uygulama ve İş Parçacığı Destek Sınıfları](../mfc/application-and-thread-support-classes.md)

   - [Komut Yönlendirme Sınıfları](../mfc/command-routing-classes.md)

   - [Belge Sınıfları](../mfc/document-classes.md)

   - [Görünüm Sınıfları (Mimari)](../mfc/view-classes-architecture.md)

   - [Çerçeve Penceresi Sınıfları (Mimari)](../mfc/frame-window-classes-architecture.md)

   - [Belge Şablonu Sınıfları](../mfc/document-template-classes.md)

- [Pencere, İletişim Kutusu ve Denetim Sınıfları](../mfc/window-dialog-and-control-classes.md)

   - [Çerçeve Penceresi Sınıfları (Windows)](../mfc/frame-window-classes-windows.md)

   - [Görünüm Sınıfları (Windows)](../mfc/view-classes-windows.md)

   - [İletişim Kutusu Sınıfları](../mfc/dialog-box-classes.md)

   - [Denetim Sınıfları](../mfc/control-classes.md)

   - [Denetim Çubuğu Sınıfları](../mfc/control-bar-classes.md)

- [Sınıf Çizme ve Boyama](../mfc/drawing-and-printing-classes.md)

   - [Çıktı (Cihaz Bağlamı) Sınıfları](../mfc/output-device-context-classes.md)

   - [Çizim Aracı Sınıfları](../mfc/drawing-tool-classes.md)

- [Basit Veri Türü Sınıfları](../mfc/simple-data-type-classes.md)

- [Dizi, Liste ve Eşleme Sınıfları](../mfc/array-list-and-map-classes.md)

   - [Diziler, Listeler ve Eşlemeler için Şablon Sınıfları](../mfc/template-classes-for-arrays-lists-and-maps.md)

   - [Kullanıma Hazır Dizi Sınıfları](../mfc/ready-to-use-array-classes.md)

   - [Kullanıma Hazır Liste Sınıfları](../mfc/ready-to-use-list-classes.md)

   - [Kullanıma Hazır Eşleme Sınıfları](../mfc/ready-to-use-map-classes.md)

- [Dosya ve Veritabanı Sınıfları](../mfc/file-and-database-classes.md)

   - [Dosya g/ç sınıfları](../mfc/file-i-o-classes.md)

   - [DAO Sınıfları](../mfc/dao-classes.md)

   - [ODBC Sınıfları](../mfc/odbc-classes.md)

   - [OLE DB Sınıfları](../mfc/ole-db-classes.md)

- [İnternet ve Ağ Sınıfları](../mfc/internet-and-networking-classes.md)

   - [Windows Yuvaları: Sınıflar](../mfc/windows-sockets-classes.md)

   - [Win32 Internet Sınıfları](../mfc/win32-internet-classes.md)

- [OLE Sınıfları](../mfc/ole-classes.md)

   - [OLE Kapsayıcı Sınıfları](../mfc/ole-container-classes.md)

   - [OLE Sunucu Sınıfları](../mfc/ole-server-classes.md)

   - [OLE Sürükle/Bırak ve Veri Aktarımı Sınıfları](../mfc/ole-drag-and-drop-and-data-transfer-classes.md)

   - [OLE Ortak İletişim Kutusu Sınıfları](../mfc/ole-common-dialog-classes.md)

   - [OLE Otomasyon Sınıfları](../mfc/ole-automation-classes.md)

   - [OLE Denetim Sınıfları](../mfc/ole-control-classes.md)

   - [Etkin Belge Sınıfları](../mfc/active-document-classes.md)

   - [OLE İle İlgili Sınıflar](../mfc/ole-related-classes.md)

- [Hata Ayıklama ve Özel Durum Sınıfları](../mfc/debugging-and-exception-classes.md)

   - [Destek Sınıflarında Hata Ayıklama](../mfc/debugging-support-classes.md)

   - [Özel Durum Sınıfları](../mfc/exception-classes.md)

Bölüm [genel sınıf tasarımı felsefesi](../mfc/general-class-design-philosophy.md) MFC Kitaplığı nasıl tasarlandığı açıklanır.

Framework'ün genel bakış için bkz. [yazma uygulamaları için Windows için sınıfları kullanma](../mfc/using-the-classes-to-write-applications-for-windows.md). Bazı yukarıda listelenen sınıflar çerçevenin dışında kullanılan ve koleksiyonlar, özel durumlar, dosyalar ve dizeler gibi kullanışlı soyut öğelerdir sağlayan genel amaçlı sınıflardır.

Bir sınıfın kalıtımını görmek için [sınıf hiyerarşisi grafiği](../mfc/hierarchy-chart.md).

Bu genel bakışta listelenen sınıflara ek olarak MFC Kitaplığı genel işlevleri, genel değişken ve makro içerir. Bir genel bakış ve bu konudaki ayrıntılı listesi [MFC makroları ve genel öğeleri](../mfc/reference/mfc-macros-and-globals.md), izler ve MFC sınıflarına alfabetik başvuru.

## <a name="see-also"></a>Ayrıca bkz.

[MFC Masaüstü Uygulamaları](../mfc/mfc-desktop-applications.md)
