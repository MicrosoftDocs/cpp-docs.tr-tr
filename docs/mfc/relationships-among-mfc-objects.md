---
title: MFC nesneleri arasındaki ilişkileri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a0cdc4ebeab81a0eb69b96b161350f75ebc8b14
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="relationships-among-mfc-objects"></a>MFC Nesneleri Arasındaki İlişki
Belge/görünüm oluşturma işlemi perspektife put yardımcı olmak için çalışan bir program göz önünde bulundurun: belge, görünüm kapsamak için kullanılmış çerçeve penceresi ve belgeyle ilişkilendirilen görünüm.  
  
-   Bir belgenin belge oluşturulan belge şablonu belge ve bir işaretçi görünümlerini listesini tutar.  
  
-   Bir görünüm için belgeyi bir işaretçi tutar ve kendi üst çerçeve penceresi alt.  
  
-   Belge çerçeve penceresi, geçerli etkin görünüm için bir işaretçi tutar.  
  
-   Belge şablonu açık kendi belgelerinin bir listesini tutar.  
  
-   Uygulamanın kendi belge şablonları listesini tutar.  
  
-   Windows açık olan tüm pencereleri onlara iletileri gönderebilmek için izler.  
  
 Bu ilişkileri belge/görünüm oluşturma sırasında oluşturulur. Aşağıdaki tabloda, çalışan bir program nesneleri diğer nesnelerin nasıl erişebileceğinizi gösterir. Herhangi bir nesne application nesnesi için bir işaretçi genel işlevini çağırarak edinebilirsiniz [AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp).  
  
### <a name="gaining-access-to-other-objects-in-your-application"></a>Uygulamanızdaki diğer nesnelere erişimini  
  
|Nesnesinden|Diğer nesnelere erişmek nasıl|  
|-----------------|---------------------------------|  
|Belge|Kullanım [GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition) ve [GetNextView](../mfc/reference/cdocument-class.md#getnextview) belgenin görünümü listesi erişmek için.<br /><br /> Çağrı [GetDocTemplate](../mfc/reference/cdocument-class.md#getdoctemplate) belge şablonu alınamıyor.|  
|Görüntüle|Çağrı [GetDocument](../mfc/reference/cview-class.md#getdocument) belge alınamıyor.<br /><br /> Çağrı [GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe) çerçeve penceresi alınamıyor.|  
|Belge çerçeve penceresi|Çağrı [GetActiveView](../mfc/reference/cframewnd-class.md#getactiveview) geçerli görünümü almak için.<br /><br /> Çağrı [GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument) geçerli görünüme bağlı belge alınamıyor.|  
|MDI çerçeve penceresi|Çağrı [MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive) şu anda etkin almak için [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md).|  
  
 Genellikle, bir çerçeve penceresinde bir görünüme sahiptir, ancak bazı durumlarda, bölümlendirici pencereler olduğu gibi aynı çerçeve penceresi birden çok görünüm içerir. Çerçeve penceresi şu anda etkin görünümün bir işaretçi tutar; İşaretçinin başka bir görünüm etkinleştirilmiş her zaman güncelleştirilir.  
  
> [!NOTE]
>  Ana çerçeve penceresi için bir işaretçi depolanan [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) üye değişkeni uygulama nesnesi. Çağrı `OnFileNew` geçersiz kılma içinde `InitInstance` üye işlevini `CWinApp` ayarlar `m_pMainWnd` sizin için. Değil çağırırsanız `OnFileNew`, değişkenin değerini ayarlamanız gerekir `InitInstance` kendiniz. (/Embedding komut satırında ise SDI COM bileşeni (sunucu) uygulamaları değişkeni ayarlamaz.) Unutmayın `m_pMainWnd` şimdi sınıf üyesi olan `CWinThread` yerine `CWinApp`.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Belge şablonları ve belge/görünüm oluşturma işlemi](../mfc/document-templates-and-the-document-view-creation-process.md)   
 [Belge şablonu oluşturma](../mfc/document-template-creation.md)   
 [Belge/görünüm oluşturma](../mfc/document-view-creation.md)   
 [Yeni Belgeler, Pencereler ve Görünümler Oluşturma](../mfc/creating-new-documents-windows-and-views.md)

