---
description: 'Daha fazla bilgi edinin: MFC nesneleri arasındaki Ilişkiler'
title: MFC Nesneleri Arasındaki İlişki
ms.date: 11/04/2016
helpviewer_keywords:
- MFC, relationships between key objects
- objects [MFC], relationships
- relationships, MFC objects
- MFC object relationships
ms.assetid: 6e8f3b51-e80f-4d88-94c8-4c1e4ee163ad
ms.openlocfilehash: 0646d487d1d60293461316edddcb97fde30905a8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218062"
---
# <a name="relationships-among-mfc-objects"></a>MFC Nesneleri Arasındaki İlişki

Belge/görünüm oluşturma işlemini perspektifte koymaya yardımcı olmak için çalışan bir programı düşünün: bir belge, görünümü içermesi için kullanılan çerçeve penceresi ve belgeyle ilişkili görünüm.

- Bir belge, bu belgenin görünümlerinin listesini ve belgeyi oluşturan belge şablonuna yönelik bir işaretçi tutar.

- Bir görünüm, kendi belgesi için bir işaretçi tutar ve üst çerçeve penceresinin alt öğesidir.

- Belge çerçevesi penceresi, geçerli etkin görünümü için bir işaretçi tutar.

- Belge şablonu, açık belgelerinin bir listesini tutar.

- Uygulama, belge şablonlarının bir listesini tutar.

- Windows, tüm açık pencereleri izleyerek onlara ileti gönderebilmesini sağlar.

Bu ilişkiler belge/görünüm oluşturma sırasında oluşturulur. Aşağıdaki tabloda, çalışan bir programdaki nesnelerin diğer nesnelere nasıl erişebileceği gösterilmektedir. Herhangi bir nesne, [AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp)genel işlevini çağırarak uygulama nesnesine bir işaretçi alabilir.

### <a name="gaining-access-to-other-objects-in-your-application"></a>Uygulamanızdaki diğer nesnelere erişim elde etme

|Nesnesinden|Diğer nesnelere erişme|
|-----------------|---------------------------------|
|Belge|Belgenin görünüm listesine erişmek için [GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition) ve [GetNextView](../mfc/reference/cdocument-class.md#getnextview) kullanın.<br /><br /> Belge şablonunu almak için [GetDocTemplate](../mfc/reference/cdocument-class.md#getdoctemplate) 'i çağırın.|
|Görüntüle|Belgeyi almak için [GetDocument](../mfc/reference/cview-class.md#getdocument) öğesini çağırın.<br /><br /> Çerçeve penceresini almak için [GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe) öğesini çağırın.|
|Belge çerçevesi penceresi|Geçerli görünümü almak için [GetActiveView](../mfc/reference/cframewnd-class.md#getactiveview) öğesini çağırın.<br /><br /> Geçerli görünüme iliştirilmiş belgeyi almak için [GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument) öğesini çağırın.|
|MDI çerçevesi penceresi|Şu anda etkin olan [Cmdictepdwnd](../mfc/reference/cmdichildwnd-class.md)'i almak Için [MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive) çağırın.|

Genellikle, bir çerçeve penceresinde tek bir görünüm bulunur, ancak bazı durumlarda bölünmüş pencereler gibi, aynı çerçeve penceresi birden çok görünüm içerir. Çerçeve penceresi, geçerli etkin görünüme bir işaretçi tutar; işaretçi, başka bir görünüm etkinleştirildiğinde güncellenir.

> [!NOTE]
> Ana çerçeve penceresine yönelik bir işaretçi, uygulama nesnesinin [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) üye değişkeninde depolanır. `OnFileNew`' Nin üye işlevini geçersiz kılmanızda ' A bir çağrı `InitInstance` `CWinApp` sizin için *m_pMainWnd* . Öğesini çağırmayın `OnFileNew` , değişkenin değerini kendiniz ayarlamanız gerekir `InitInstance` . (/Gömme komut satıralıyorsa, SDI COM bileşeni (sunucu) uygulamaları değişkeni ayarlayamayabilir.) *M_pMainWnd* artık yerine sınıfının bir üyesi olduğunu unutmayın `CWinThread` `CWinApp` .

## <a name="see-also"></a>Ayrıca bkz.

[Belge şablonları ve belge/görünüm oluşturma Işlemi](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Belge şablonu oluşturma](../mfc/document-template-creation.md)<br/>
[Belge/görünüm oluşturma](../mfc/document-view-creation.md)<br/>
[Yeni belgeler, pencereler ve görünümler oluşturma](../mfc/creating-new-documents-windows-and-views.md)
