---
title: MFC'de Kullanılabilen Türetilmiş Görünüm Sınıfları
ms.date: 11/04/2016
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
ms.openlocfilehash: 61b38f6147a8bde4f6eb42cd144f9f64dac8dbd8
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269298"
---
# <a name="derived-view-classes-available-in-mfc"></a>MFC'de Kullanılabilen Türetilmiş Görünüm Sınıfları

Aşağıdaki tablo, MFC'nin görünümü sınıflar ve ilişkileri birbirine gösterir. Özellikler Görünümü sınıfınızın kendisinden türetilen MFC görünüm sınıfı bağlıdır.

### <a name="view-classes"></a>Görünüm sınıfları

|örneği|Açıklama|
|-----------|-----------------|
|[CView](../mfc/reference/cview-class.md)|Tüm görünümler taban sınıfı.|
|[CCtrlView](../mfc/reference/cctrlview-class.md)|Taban sınıfının `CTreeView`, `CListView`, `CEditView`, ve `CRichEditView`. Bu sınıfların belge/görünüm mimarisi ile belirtilen Windows ortak denetimleri kullanmanıza izin verir.|
|[CEditView](../mfc/reference/ceditview-class.md)|Üzerinde Windows tabanlı basit bir görünüm düzenleme kutusu denetimi. Metin girme ve düzenleme sağlar ve basit metin düzenleyici uygulaması için temel olarak kullanılabilir. Ayrıca bkz: `CRichEditView`.|
|[CRichEditView](../mfc/reference/cricheditview-class.md)|Bir görünüm içeren bir [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) nesne. Bu sınıf için benzer `CEditView`, ancak tersine `CEditView`, `CRichEditView` tanıtıcıları biçimlendirilmiş metin.|
|[CListView](../mfc/reference/clistview-class.md)|Bir görünüm içeren bir [CListCtrl](../mfc/reference/clistctrl-class.md) nesne.|
|[CTreeView](../mfc/reference/ctreeview-class.md)|Bir görünüm içeren bir [CTreeCtrl](../mfc/reference/ctreectrl-class.md) Visual C++ Çözüm Gezgini penceresinde benzer görünümleri için bir nesne.|
|[CScrollView](../mfc/reference/cscrollview-class.md)|Taban sınıfının `CFormView`, `CRecordView`, ve `CDaoRecordView`. Görünümün içeriğini kaydırma uygular.|
|[CFormView](../mfc/reference/cformview-class.md)|Bir form görünümü denetimleri içeren bir görünümü. Form tabanlı bir uygulama bir veya daha fazla tür form arabirimleri sağlar.|
|[CHtmlView](../mfc/reference/chtmlview-class.md)|Bir Web tarayıcı görünümü ile uygulamanın kullanıcı klasörleri yanı sıra World Wide Web sitelerinde yerel dosya sistemi ve ağ üzerinde göz atabilirsiniz. Web tarayıcı görünümü ayrıca bir etkin belge kapsayıcısı çalışabilir.|
|[CRecordView](../mfc/reference/crecordview-class.md)|Denetimlerinde ODBC veritabanı kayıtlarını görüntüleyen bir form görünümü. Projenizde ODBC desteği seçerseniz, görünüm temel sınıfı olan `CRecordView`. Görünüm bağlı bir `CRowset` nesne.|
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|Denetimlerinde DAO veritabanı kayıtlarını görüntüleyen bir form görünümü. DAO destek projenizde seçerseniz, görünüm temel sınıftır `CDaoRecordView`. Görünüm bağlı bir `CDaoRecordset` nesne.|
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|OLE DB kayıt denetimlerinde görüntüleyen bir form görünümü. Projenizde OLE DB desteği seçerseniz, görünüm temel sınıfı olan `COleDBRecordView`. Görünüm bağlı bir `CRowset` nesne.|

> [!NOTE]
>  MFC sürüm 4.0 itibariyle `CEditView` türetilir `CCtrlView`.

Bu sınıfların kullanmak için onlardan uygulamanın görünüm sınıfları türetin. İlgili bilgiler için bkz. [kaydırma ve ölçeklendirme görünümleri](../mfc/scrolling-and-scaling-views.md). Veritabanı sınıfları hakkında daha fazla bilgi için bkz. [genel bakış: Veritabanı programlama](../data/data-access-programming-mfc-atl.md).

## <a name="see-also"></a>Ayrıca bkz.

[Görünümleri Kullanma](../mfc/using-views.md)
