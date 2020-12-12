---
description: 'Daha fazla bilgi edinin: MFC makroları ve genel'
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
ms.openlocfilehash: 9e3d3acd74d1cf6db5856432cdefd632e36185f3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97219154"
---
# <a name="mfc-macros-and-globals"></a>MFC Makroları ve Genel Öğeleri

Microsoft Foundation Class Kitaplığı iki ana bölüme ayrılabilir: (1) MFC sınıfları ve (2) makroları ve genel. Bir işlev veya değişken bir sınıfın üyesi değilse, genel bir işlev veya değişkendir.

MFC kitaplığı ve etkin şablon kitaplığı (ATL), dize dönüştürme makrolarını paylaşır. Daha fazla bilgi için, ATL belgelerindeki [dize dönüştürme makroları](../../atl/reference/string-conversion-macros.md) bölümüne bakın.

Aşağıdaki kategorilerdeki MFC makroları ve genel teklif işlevleri.

## <a name="general-mfc"></a>Genel MFC

- [Veri türleri](data-types-mfc.md)

- [MFC sınıf nesnelerine ilişkin tür atama](type-casting-of-mfc-class-objects.md)

- [Çalışma süresi nesne modeli hizmetleri](run-time-object-model-services.md)

- [Tanı hizmetleri](diagnostic-services.md)

- [Özel durum işleme](exception-processing.md)

- [CString biçimlendirmesi ve ileti kutusu görüntüleme](cstring-formatting-and-message-box-display.md)

- [İleti eşlemeleri](message-map-macros-mfc.md)

- [Temsilci ve arabirim haritaları](delegate-and-interface-maps.md)

- [Modüller ve DLL'ler](extension-dll-macros.md)

- [Uygulama bilgileri ve yönetimi](application-information-and-management.md)

- [Standart komut ve pencere kimlikleri](standard-command-and-window-ids.md)

- [Koleksiyon sınıfı yardımcıları](collection-class-helpers.md)

- [Gri ve titremeli bit eşlem işlevleri](gray-and-dithered-bitmap-functions.md)

- [Standart iletişim kutusu veri değişimi (DDX) yordamları](standard-dialog-data-exchange-routines.md)

- [Standart iletişim kutusu veri doğrulama (DDV) yordamları](standard-dialog-data-validation-routines.md)

- [AFX Iletileri](afx-messages.md)

- [ToolBar denetim stilleri](toolbar-control-styles.md)

- [CMFCImagePaintArea:: IMAGE_EDIT_MODE numaralandırması](cmfcimagepaintarea-image-edit-mode-enumeration.md)

## <a name="database"></a>Veritabanı

- MFC ODBC sınıfları için [kayıt alanı değişimi (RFX) işlevleri](record-field-exchange-functions.md) ve [toplu kayıt alanı DEĞIŞIMI (toplu RFX) işlevleri](record-field-exchange-functions.md)

- MFC DAO sınıfları için [kayıt alanı değişimi (DFX) işlevleri](record-field-exchange-functions.md)

- [CRecordView ve CDaoRecordView Için Iletişim kutusu veri değişimi (DDX) işlevleri](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (MFC ODBC ve DAO sınıfları)

- [OLE denetimleri için iletişim kutusu veri değişimi (DDX) işlevleri](dialog-data-exchange-functions-for-ole-controls.md)

- [Açık veritabanı bağlantısı (ODBC) API işlevlerini doğrudan çağırmaya yardımcı olacak makrolar ve genel](database-macros-and-globals.md)

- [DAO veritabanı motoru başlatma ve sonlandırma](dao-database-engine-initialization-and-termination.md)

## <a name="internet"></a>İnternet

- [İnternet URL ayrıştırma genel öğeleri](internet-url-parsing-globals.md)

## <a name="dhtml--dhtml-event-maps"></a>DHTML/DHTML olay haritaları

- [DHTML iletişim kutusu veri değişimi (DDX) Yardımcısı makroları](ddx-dhtml-helper-macros.md)

- [DHTML olay eşlemeleri](dhtml-event-maps.md)

## <a name="ole"></a>OLE

- [OLE başlatma](ole-initialization.md)

- [Uygulama denetimi](application-control.md)

- [Eşlemeleri dağıtma](dispatch-maps.md)

Ayrıca, MFC, katıştırılmış OLE denetimlerini tam olarak desteklemek için MFC 4,0 ile geliştirilen herhangi bir OLE kapsayıcısını sağlayan [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) adlı bir işlev sağlar.

## <a name="ole-controls"></a>OLE denetimleri

- [Değişken parametre türü sabitleri](variant-parameter-type-constants.md)

- [Tür kitaplığı erişimi](type-library-access.md)

- [Özellik sayfaları](property-pages-mfc.md)

- [Olay eşlemeleri](event-maps.md)

- [Olay iç havuz eşlemeleri](event-sink-maps.md)

- [Bağlantı eşlemeleri](connection-maps.md)

- [OLE denetimlerini kaydetme](registering-ole-controls.md)

- [Sınıf oluşturucular ve lisanslama](class-factories-and-licensing.md)

- [OLE denetimlerinin kalıcılığı](persistence-of-ole-controls.md)

Bu bölümün ilk bölümü, önceki kategorilerin her birini kısaca ele alır ve ilgili kısa açıklama açıklamalarıyla birlikte kategoride genel ve makroları listeler. Bu, MFC kitaplığındaki genel işlevlerin, genel değişkenlerin ve makroların açıklamalarıdır.

> [!NOTE]
> Birçok genel işlev "AFX" önekiyle başlar ancak bazı, örneğin, iletişim kutusu veri değişimi (DDX) işlevleri ve veritabanı işlevlerinin birçoğu, bu kuralı takip etmez. Tüm genel değişkenler ön ek olarak "AFX" ile başlar. Makrolar belirli bir ön ek ile başlamaz, ancak büyük harflerle yazılır.

## <a name="see-also"></a>Ayrıca bkz.

[Sınıfa genel bakış](../../mfc/class-library-overview.md)
