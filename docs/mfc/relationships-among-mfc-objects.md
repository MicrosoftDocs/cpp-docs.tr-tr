---
title: MFC nesneleri arasındaki ilişkiler | Microsoft Docs
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
ms.openlocfilehash: d2f42f754157a4fc2e3f3e1aa40f38477b982e16
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46372489"
---
# <a name="relationships-among-mfc-objects"></a>MFC Nesneleri Arasındaki İlişki

Belge/görünüm oluşturma işlemi açıdan bakın yardımcı olmak için çalışan bir program göz önünde bulundurun: bir belge, görünüm kapsamak için kullanılmış çerçeve penceresi ve belgeyle ilişkili görünüm.

- Bir belge, belgeyi oluşturan bir belge şablonu belge ve bir işaretçi görünümlerini listesini tutar.

- Bir görünüm, belgeye bir işaretçi tutar ve kendi ana çerçeve penceresinin bir alt öğesidir.

- Belge çerçeve penceresi, geçerli etkin görünüm için bir işaretçi tutar.

- Bir belge şablonu, açık belgelerin listesini tutar.

- Uygulama, belge şablonları listesini tutar.

- Windows tüm pencereler için İleti gönderebilmek için izler.

Bu ilişkiler belge/görünüm oluşturma sırasında oluşturulur. Aşağıdaki tabloda, çalışan bir program nesneleri diğer nesnelerin nasıl erişeceği gösterilmektedir. Genel bir işlev çağırarak application nesnesine bir işaretçi herhangi bir nesne elde edebilirsiniz [AfxGetApp](../mfc/reference/application-information-and-management.md#afxgetapp).

### <a name="gaining-access-to-other-objects-in-your-application"></a>Uygulamanızdaki diğer nesnelere erişim elde etme

|Nesneden|Diğer nesnelere erişmek nasıl|
|-----------------|---------------------------------|
|Belge|Kullanım [GetFirstViewPosition](../mfc/reference/cdocument-class.md#getfirstviewposition) ve [GetNextView](../mfc/reference/cdocument-class.md#getnextview) belge görünümü listesine erişmek için.<br /><br /> Çağrı [GetDocTemplate](../mfc/reference/cdocument-class.md#getdoctemplate) belgeler alınamıyor.|
|Görüntüle|Çağrı [GetDocument](../mfc/reference/cview-class.md#getdocument) belge alınamıyor.<br /><br /> Çağrı [GetParentFrame](../mfc/reference/cwnd-class.md#getparentframe) çerçeve penceresi alınamıyor.|
|Belge çerçeve penceresi|Çağrı [GetActiveView](../mfc/reference/cframewnd-class.md#getactiveview) geçerli bir görünüm elde edin.<br /><br /> Çağrı [GetActiveDocument](../mfc/reference/cframewnd-class.md#getactivedocument) geçerli görünüme iliştirilmiş belgeye alınamıyor.|
|MDI çerçeve penceresi|Çağrı [MDIGetActive](../mfc/reference/cmdiframewnd-class.md#mdigetactive) etkin almak için [Cmdıchildwnd](../mfc/reference/cmdichildwnd-class.md).|

Genellikle, tek bir görünümde bir çerçeve penceresi sahiptir, ancak bazı durumlarda, bölümlendirici pencereler olduğu gibi aynı çerçeve penceresi birden çok görünüm içerir. Çerçeve penceresi şu anda etkin görünüm için bir işaretçi tutar; İşaretçiyi, başka bir görünüme etkinleştirilir dilediğiniz zaman güncelleştirilir.

> [!NOTE]
>  Ana çerçeve penceresine bir işaretçi depolanan [m_pMainWnd](../mfc/reference/cwinthread-class.md#m_pmainwnd) üye değişkeni uygulama nesnesi. Bir çağrı `OnFileNew` kılacağınızı içinde `InitInstance` üye işlevinin `CWinApp` ayarlar *m_pMainWnd* sizin için. Değil çağırırsanız `OnFileNew`, değişkenin değeri ayarlamanız gerekir `InitInstance` kendiniz. (Komut satırında/Embedding ise SDI COM bileşeni (sunucu) uygulamaları değişkeni ayarlanmamış.) Unutmayın *m_pMainWnd* artık sınıfın bir üyesidir `CWinThread` yerine `CWinApp`.

## <a name="see-also"></a>Ayrıca Bkz.

[Belge şablonları ve belge/görünüm oluşturma işlemi](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Belge Şablonu Oluşturma](../mfc/document-template-creation.md)<br/>
[Belge/görünüm oluşturma](../mfc/document-view-creation.md)<br/>
[Yeni Belgeler, Pencereler ve Görünümler Oluşturma](../mfc/creating-new-documents-windows-and-views.md)

