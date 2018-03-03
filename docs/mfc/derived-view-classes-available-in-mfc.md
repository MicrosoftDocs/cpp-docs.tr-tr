---
title: "View sınıfları MFC'de kullanılabilen türetilmiş | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CView class [MFC], classes derived from
- classes [MFC], derived
- derived classes [MFC], view classes
- view classes [MFC], derived
ms.assetid: dba42178-7459-4ccc-b025-f3d9b8a4b737
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2426f3e547da6eaab6a4b38bb5199e87c93ef933
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="derived-view-classes-available-in-mfc"></a>MFC'de Kullanılabilen Türetilmiş Görünüm Sınıfları
Aşağıdaki tabloda MFC'nin görünümü sınıfları ve birbirleriyle ilişkilerini gösterir. View sınıfı özelliklerini kendisinden türetilen MFC görünüm sınıfı bağlıdır.  
  
### <a name="view-classes"></a>View sınıfları  
  
|örneği|Açıklama|  
|-----------|-----------------|  
|[CView](../mfc/reference/cview-class.md)|Tüm görünümleri temel sınıfı.|  
|[CCtrlView](../mfc/reference/cctrlview-class.md)|Temel sınıfının `CTreeView`, `CListView`, `CEditView`, ve `CRichEditView`. Bu sınıfların belge/görünüm mimarisi ile belirtilen Windows ortak denetimleri kullanmanıza olanak tanır.|  
|[CEditView](../mfc/reference/ceditview-class.md)|Windows tabanlı basit bir görünümü düzenleme kutusu denetimi. Metin girme ve düzenleme sağlar ve basit bir metin düzenleyici uygulaması için temel olarak kullanılabilir. Ayrıca bkz. `CRichEditView`.|  
|[CRichEditView](../mfc/reference/cricheditview-class.md)|Bir görünüm içeren bir [CRichEditCtrl](../mfc/reference/cricheditctrl-class.md) nesnesi. Bu sınıf için paraleldir `CEditView`, ancak aksine `CEditView`, `CRichEditView` tanıtıcıları biçimlendirilmiş metin.|  
|[CListView](../mfc/reference/clistview-class.md)|Bir görünüm içeren bir [CListCtrl](../mfc/reference/clistctrl-class.md) nesnesi.|  
|[CTreeView](../mfc/reference/ctreeview-class.md)|Bir görünüm içeren bir [CTreeCtrl](../mfc/reference/ctreectrl-class.md) Visual C++'ta Solution Explorer penceresi benzer görünümler için nesne.|  
|[CScrollView](../mfc/reference/cscrollview-class.md)|Temel sınıfının `CFormView`, `CRecordView`, ve `CDaoRecordView`. Görünümün içeriğini kaydırma uygular.|  
|[Cformview'yu](../mfc/reference/cformview-class.md)|Bir form görünümü, denetimleri içeren bir görünüm. Forms tabanlı bir uygulama bir veya daha fazla tür form arabirimleri sağlar.|  
|[CHtmlView](../mfc/reference/chtmlview-class.md)|Bir Web tarayıcı görünümü, uygulamanın kullanıcı klasörleri yanı sıra World Wide Web sitelerinde yerel dosya sisteminde ve ağ üzerinde göz atabilirsiniz. Web tarayıcı görünümü etkin belge kapsayıcı olarak da çalışabilir.|  
|[CRecordView](../mfc/reference/crecordview-class.md)|ODBC veritabanı kayıtlarını denetimlerinde görüntüler form görünümü. ODBC desteği projenizde seçerseniz, görünümün temel sınıftır `CRecordView`. Görünüm bağlı bir `CRowset` nesnesi.|  
|[CDaoRecordView](../mfc/reference/cdaorecordview-class.md)|DAO veritabanı kayıtlarını denetimlerinde görüntüler form görünümü. DAO destek projenizde seçerseniz, görünümün temel sınıftır `CDaoRecordView`. Görünüm bağlı bir `CDaoRecordset` nesnesi.|  
|[COleDBRecordView](../mfc/reference/coledbrecordview-class.md)|OLE DB kayıt denetimlerinde görüntüleyen bir form görünümü. OLE DB desteği projenizde seçerseniz, görünümün temel sınıftır `COleDBRecordView`. Görünüm bağlı bir `CRowset` nesnesi.|  
  
> [!NOTE]
>  MFC sürüm 4.0 itibariyle `CEditView` türetildiği `CCtrlView`.  
  
 Bu sınıfları, uygulamanızda kullanmak için uygulamanın görünümü sınıfları onlardan türetilir. İlgili bilgi için bkz: [kaydırma ve ölçeklendirme görünümleri](../mfc/scrolling-and-scaling-views.md). Veritabanı sınıfları hakkında daha fazla bilgi için bkz: [genel bakış: veritabanı programlama](../data/data-access-programming-mfc-atl.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Görünümleri Kullanma](../mfc/using-views.md)

