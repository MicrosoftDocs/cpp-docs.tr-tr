---
title: MFC Nesneleri Arasındaki İlişki
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
ms.openlocfilehash: d7e40e25b405d3f8ec50a518889cc2b89bc8c725
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372807"
---
# <a name="relationships-among-mfc-objects"></a>MFC Nesneleri Arasındaki İlişki

Belge/görünüm oluşturma işlemini perspektife koymaya yardımcı olmak için çalışan bir programı düşünün: belge, görünümü içeren çerçeve penceresi ve belgeyle ilişkili görünüm.

- Belge, o belgenin görünümlerinin bir listesini ve belgeyi oluşturan belge şablonuna işaretçi tutar.

- Görünüm, bir işaretçiyi belgeye tutar ve üst çerçeve penceresinin bir alt öğesidir.

- Belge çerçevesi penceresi, bir işaretçiyi geçerli etkin görünümüne tutar.

- Belge şablonu, açık belgelerinin listesini tutar.

- Uygulama, belge şablonlarının bir listesini tutar.

- Windows, onlara ileti gönderebilmek için tüm açık pencereleri izler.

Bu ilişkiler belge/görünüm oluşturma sırasında kurulur. Aşağıdaki tablo, çalışan bir programdaki nesnelerin diğer nesnelere nasıl erişebileceğini gösterir. Herhangi bir nesne global fonksiyon [AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp)çağırarak uygulama nesnesi için bir işaretçi elde edebilirsiniz.

### <a name="gaining-access-to-other-objects-in-your-application"></a>Başvurunuzdaki Diğer Nesnelere Erişim Sağlama

|Nesneden|Diğer nesnelere nasıl erişilir?|
|-----------------|---------------------------------|
|Belge|Belgenin görünüm listesine erişmek için [GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition) ve [GetNextView'i](../mfc/reference/cdocument-class.md#getnextview) kullanın.<br /><br /> Belge şablonuna ulaşmak için [GetDocTemplate'i](../mfc/reference/cdocument-class.md#getdoctemplate) arayın.|
|Görüntüle|Belgeyi almak için [GetDocument'i](../mfc/reference/cview-class.md#getdocument) arayın.<br /><br /> Çerçeve penceresini almak için [GetParentFrame'i](../mfc/reference/cwnd-class.md#getparentframe) arayın.|
|Belge çerçevesi penceresi|Geçerli görünümü almak için [GetActiveView'i](../mfc/reference/cframewnd-class.md#getactiveview) arayın.<br /><br /> Belgenin geçerli görünüme eklenmesi için [GetActiveDocument'i](../mfc/reference/cframewnd-class.md#getactivedocument) arayın.|
|MDI çerçeve penceresi|Şu anda etkin [CMDIChildWnd](../mfc/reference/cmdichildwnd-class.md)almak için [MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive) arayın.|

Genellikle, bir çerçeve penceresi bir görünüme sahiptir, ancak bazen, bölücü pencerelerde olduğu gibi, aynı çerçeve penceresi birden çok görünüm içerir. Çerçeve penceresi, şu anda etkin görünümü işaretçi tutar; işaretçi, başka bir görünüm etkinleştirildiğinde güncelleştirilir.

> [!NOTE]
> Ana çerçeve penceresine işaretçi, uygulama nesnesinin [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) üye değişkeninde depolanır. Kümelerin `InitInstance` üye işlevini geçersiz kılmanızda sizin için *m_pMainWnd* bir çağrı. `OnFileNew` `CWinApp` `OnFileNew`Aramazsanız, değişkenin değerini `InitInstance` kendiniz ayarlamanız gerekir. (SDI COM bileşeni (sunucu) uygulamaları komut satırında /Gömme varsa değişkeni ayarlamayabilir.) *m_pMainWnd* artık sınıfın bir üyesi `CWinThread` değil `CWinApp`de.

## <a name="see-also"></a>Ayrıca bkz.

[Belge Şablonları ve Belge/Görünüm Oluşturma İşlemi](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Belge Şablonu Oluşturma](../mfc/document-template-creation.md)<br/>
[Belge/Görünüm Oluşturma](../mfc/document-view-creation.md)<br/>
[Yeni Belgeler, Windows ve Görünümler Oluşturma](../mfc/creating-new-documents-windows-and-views.md)
