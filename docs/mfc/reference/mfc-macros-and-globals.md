---
title: "MFC makroları ve genel öğeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vc.mfc.macros
dev_langs:
- C++
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eeb53dea24ccd4d34ef90045e3254915135e70c2
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mfc-macros-and-globals"></a>MFC Makroları ve Genel Öğeleri
Microsoft Foundation Class Kitaplığı iki ana bölüme ayrılabilir: (1 MFC sınıfları ve (2) makroları ve genel öğeleri. Bir işlev veya değişken bir sınıf üyesi değilse, genel işlev veya değişken olur.  
  
 MFC kitaplığını ve Etkin Şablon kitaplığı (ATL) dize dönüşüm makroları paylaşır. Daha fazla bilgi için bkz: [dize dönüşüm makroları](../../atl/reference/string-conversion-macros.md) ATL belgelerinde.  
  
 MFC makroları ve genel öğeleri aşağıdaki kategorilerde işlevleri sunar.  
  
## <a name="general-mfc"></a>Genel MFC  
  
-   [Veri türleri](data-types-mfc.md)  
  
-   [MFC sınıf nesnelerine tür atama](type-casting-of-mfc-class-objects.md)  
  
-   [Çalışma zamanı nesne modeli Hizmetleri](run-time-object-model-services.md)  
  
-   [Tanılama Hizmetleri](diagnostic-services.md)  
  
-   [Özel durum işleme](exception-processing.md)  
  
-   [CString biçimlendirmesi ve ileti kutusu görüntüleme](cstring-formatting-and-message-box-display.md)  
  
-   [İleti eşlemeleri](message-map-macros-mfc.md)  

-   [Temsilci ve arabirim eşlemeleri](delegate-and-interface-maps.md)

-   [Modüller ve DLL'ler](extension-dll-macros.md)
  
-   [Uygulama bilgileri ve Yönetimi](application-information-and-management.md)  
  
-   [Standart komut ve pencere kimlikleri](standard-command-and-window-ids.md)  
  
-   [Koleksiyon sınıfı Yardımcıları](collection-class-helpers.md)  
  
-   [Gri ve Titremeli bit eşlem işlevleri](gray-and-dithered-bitmap-functions.md)  
  
-   [Standart iletişim kutusu veri değişimi (DDX) yordamları](standard-dialog-data-exchange-routines.md)  
  
-   [Standart iletişim kutusu veri doğrulama (DDV) yordamları](standard-dialog-data-validation-routines.md)  
  
-   [AFX İletileri](afx-messages.md)  
  
-   [ToolBar Denetim Stilleri](toolbar-control-styles.md)  
  
-   [CMFCImagePaintArea::IMAGE_EDIT_MODE Numaralandırması](cmfcimagepaintarea-image-edit-mode-enumeration.md)  

  
## <a name="database"></a>Veritabanı  
  
-   [Kayıt alanı değişimi (RFX) işlevlerini](record-field-exchange-functions.md) ve [toplu kayıt alanı değişimi (Toplu RFX) işlevleri](record-field-exchange-functions.md) MFC ODBC sınıfları  
  
-   [Kayıt alanı değişimi (DFX) işlevleri](record-field-exchange-functions.md) MFC DAO sınıfları  
  
-   [CRecordView ve CDaoRecordView için iletişim kutusu veri değişimi (DDX) işlevleri](dialog-data-exchange-functions-for-crecordview-and-cdaorecordview.md) (MFC ODBC ve DAO sınıfları)  
  
-   [OLE denetimleri için iletişim kutusu veri değişimi (DDX) işlevleri](dialog-data-exchange-functions-for-ole-controls.md)  
  
-   [Makroları ve genel öğeleri açık veritabanı bağlantısı (ODBC) API işlevlerini doğrudan çağırma yardımcı olmak için](database-macros-and-globals.md)  
  
-   [DAO veritabanı motoru başlatma ve sonlandırma](dao-database-engine-initialization-and-termination.md)  
  
## <a name="internet"></a>Internet  
  
-   [Internet URL Ayrıştırma genel öğeleri](internet-url-parsing-globals.md)  
  
## <a name="dhtml--dhtml-event-maps"></a>DHTML / DHTML olay eşlemeleri  
  
-   [DHTML iletişim kutusu veri değişimi (DDX) Yardımcısı makroları](ddx-dhtml-helper-macros.md)  
  
-   [DHTML olay eşlemeleri](dhtml-event-maps.md)  
  
## <a name="ole"></a>OLE  
  
-   [OLE başlatma](ole-initialization.md)  
  
-   [Uygulama denetimi](application-control.md)  
  
-   [Eşlemeleri dağıtma](dispatch-maps.md)  
  
 Ayrıca, MFC adlı bir işlev sağlar [AfxEnableControlContainer](ole-initialization.md#afxenablecontrolcontainer) tüm OLE kapsayıcı tam olarak desteklemek için MFC 4.0 ile geliştirilen etkinleştirir OLE denetimleri katıştırılmış.  
  
## <a name="ole-controls"></a>OLE denetimleri  
  
-   [Değişken parametre türü sabitleri](variant-parameter-type-constants.md)  
  
-   [Tür kitaplığı erişimi](type-library-access.md)  
  
-   [Özellik sayfaları](property-pages-mfc.md)  
  
-   [Olay eşlemeleri](event-maps.md)  
  
-   [Olay iç havuz eşlemeleri](event-sink-maps.md)  
  
-   [Bağlantı eşlemeleri](connection-maps.md)  
  
-   [OLE denetimlerini kaydetme](registering-ole-controls.md)  
  
-   [Sınıf oluşturucular ve lisanslama](class-factories-and-licensing.md)  
  
-   [OLE denetimlerinin kalıcılığı](persistence-of-ole-controls.md)  
  
 Bu bölümde ilk bölümü kısaca önceki kategorilerden her biri açıklanır ve işlevlerin kısa açıklamaları birlikte kategorisinde makroları ve genel öğeleri listeler. Bu aşağıdaki genel işlevler, genel değişkenler ve MFC Kitaplığı'nda makroları açıklamalardır.  
  
> [!NOTE]
>  Birçok genel işlevler "Afx" önekiyle başlayan, ancak bazı, örneğin, iletişim kutusu veri değişimi (DDX) işlevleri ve çoğu veritabanı işlevleri bu kuralı izlemeyin. Tüm genel değişkenler "afx" ile bir önek olarak başlatın. Makrolar herhangi belirli önek ile başlamaz, ancak büyük harflerle yazılır.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Sınıfa genel bakış](../../mfc/class-library-overview.md)



