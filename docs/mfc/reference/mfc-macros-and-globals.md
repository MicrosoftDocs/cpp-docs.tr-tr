---
title: MFC Makroları ve Genel Öğeleri
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, global functions and variables
- MFC, macros
- global functions, MFC
- macros, MFC
- global functions [MFC]
- global variables, MFC
- Afx naming convention
- macros
ms.assetid: add4e33f-0e62-4d27-be14-896cb8675d22
ms.openlocfilehash: ed45fc7014bda18887be6dc8fbcdff8ba9a9c5f1
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373050"
---
# <a name="mfc-macros-and-globals"></a>MFC Makroları ve Genel Öğeleri

Microsoft Hazırlık Sınıf Kitaplığı iki ana bölüme ayrılabilir: (1) MFC sınıfları ve (2) makrolar ve küreseller. Bir işlev veya değişken bir sınıfın üyesi değilse, bu genel bir işlev veya değişkendir.

MFC kitaplığı ve Etkin Şablon Kitaplığı (ATL) dize dönüştürme makrolarını paylaşır. Daha fazla bilgi için ATL belgelerinde [String Dönüşüm Makroları'na](../../atl/reference/string-conversion-macros.md) bakın.

MFC makroları ve globalleri aşağıdaki kategorilerde işlevsellik sunar.

## <a name="general-mfc"></a>Genel MFC

- [Veri türleri](data-types-mfc.md)

- [MFC sınıf nesnelerine ilişkin tür atama](type-casting-of-mfc-class-objects.md)

- [Çalışma süresi nesne modeli hizmetleri](run-time-object-model-services.md)

- [Tanı hizmetleri](diagnostic-services.md)

- [Özel durum işleme](exception-processing.md)

- [CString biçimlendirme ve ileti kutusu ekranı](cstring-formatting-and-message-box-display.md)

- [İleti eşlemeleri](message-map-macros-mfc.md)

- [Temsilci ve Arayüz Haritaları](delegate-and-interface-maps.md)

- [Modüller ve DLL'ler](extension-dll-macros.md)

- [Uygulama bilgileri ve yönetimi](application-information-and-management.md)

- [Standart komut ve pencere kimlikleri](standard-command-and-window-ids.md)

- [Toplama sınıfı yardımcıları](collection-class-helpers.md)

- [Gri ve dithered bitmap işlevleri](gray-and-dithered-bitmap-functions.md)

- [Standart iletişim veri alışverişi (DDX) yordamları](standard-dialog-data-exchange-routines.md)

- [Standart iletişim veri doğrulama (DDV) yordamları](standard-dialog-data-validation-routines.md)

- [AFX Mesajları](afx-messages.md)

- [ToolBar Denetim Stilleri](toolbar-control-styles.md)

- [CMFCImagePaintArea::IMAGE_EDIT_MODE Numaralandırma](cmfcimagepaintarea-image-edit-mode-enumeration.md)

## <a name="database"></a>Veritabanı

- MFC ODBC sınıfları için [Kayıt Alanı Değişimi (RFX) fonksiyonları](record-field-exchange-functions.md) ve Toplu Kayıt Alanı Değişimi [(toplu RFX) işlevleri](record-field-exchange-functions.md)

- MFC DAO sınıfları için [kayıt alanı değişimi (DFX) işlevleri](record-field-exchange-functions.md)

- [CRecordView ve CDaoRecordView](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (MFC ODBC ve DAO sınıfları) için iletişim veri alışverişi (DDX) işlevleri

- [OLE denetimleri için iletişim veri alışverişi (DDX) işlevleri](dialog-data-exchange-functions-for-ole-controls.md)

- [Açık Veritabanı Bağlantısı (ODBC) API işlevlerini doğrudan aramada yardımcı olmak için makrolar ve küreseller](database-macros-and-globals.md)

- [DAO veritabanı motoru başlatma ve sonlandırma](dao-database-engine-initialization-and-termination.md)

## <a name="internet"></a>Internet

- [İnternet URL ayrıştırma genel öğeleri](internet-url-parsing-globals.md)

## <a name="dhtml--dhtml-event-maps"></a>DHTML / DHTML Etkinlik Haritaları

- [DHTML iletişim veri alışverişi (DDX) yardımcı makroları](ddx-dhtml-helper-macros.md)

- [DHTML olay haritaları](dhtml-event-maps.md)

## <a name="ole"></a>OLE

- [OLE başlatma](ole-initialization.md)

- [Uygulama kontrolü](application-control.md)

- [Haritaları gönder](dispatch-maps.md)

Buna ek olarak, MFC, MFC 4.0 ile geliştirilen herhangi bir OLE kapsayıcının gömülü OLE denetimlerini tam olarak desteklemesini sağlayan [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) adlı bir işlev sağlar.

## <a name="ole-controls"></a>OLE Kontrolleri

- [Değişken parametre türü sabitleri](variant-parameter-type-constants.md)

- [Tür kitaplığı erişimi](type-library-access.md)

- [Özellik sayfaları](property-pages-mfc.md)

- [Olay eşlemeleri](event-maps.md)

- [Olay iç havuz eşlemeleri](event-sink-maps.md)

- [Bağlantı eşlemeleri](connection-maps.md)

- [OLE denetimlerini kaydetme](registering-ole-controls.md)

- [Sınıf oluşturucular ve lisanslama](class-factories-and-licensing.md)

- [OLE kontrollerinin kalıcılığı](persistence-of-ole-controls.md)

Bu bölümün ilk bölümünde, önceki kategorilerin her biri kısaca açıklanıyor ve işlevselliğin kısa açıklamalarıyla birlikte kategorideki genel leri ve makroları listeler. Bunu, MFC kitaplığındaki genel işlevlerin, genel değişkenlerin ve makroların açıklamaları aşağıda veda eder.

> [!NOTE]
> Birçok genel işlev "Afx" önekiyle başlar, ancak bazıları, örneğin, iletişim veri alışverişi (DDX) işlevleri ve veritabanı işlevlerinin çoğu bu kuralı izlemez. Tüm global değişkenler önek olarak "afx" ile başlar. Makrolar belirli bir önek ile başlamaz, ancak büyük harflerle yazılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa Genel Bakış](../../mfc/class-library-overview.md)
