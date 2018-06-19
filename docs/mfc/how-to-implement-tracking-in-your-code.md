---
title: 'Nasıl yapılır: kodunuzda izleme | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CRectTracker class [MFC], implementing trackers
ms.assetid: baaeca2c-5114-485f-bf58-8807db1bc973
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bae9696be10ab00a076a73c14281a9baabe3d6d8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33349742"
---
# <a name="how-to-implement-tracking-in-your-code"></a>Nasıl yapılır: Kodunuzda İzleme Uygulama
OLE öğe izlemek için öğeyi tıklatarak veya belgenin görünümünü güncelleştirme gibi öğesine ilgili belirli olayları işlemesi gerekir. Her durumda, geçici bir bildirmek yeterli [CRectTracker](../mfc/reference/crecttracker-class.md) bu nesnesi yoluyla öğesi nesne ve.  
  
 Bir kullanıcı bir öğeyi seçer veya menü komutu ile bir nesne ekler, OLE öğesi durumunu göstermek için uygun stilleri izleyiciyle başlatması gerekir. Aşağıdaki tabloda OCLIENT örnek tarafından kullanılan kuralları açıklar. Bu stiller hakkında daha fazla bilgi için bkz: `CRectTracker`.  
  
### <a name="container-styles-and-states-of-the-ole-item"></a>Kapsayıcı stilleri ve OLE öğesi durumları  
  
|Görüntülenen stili|OLE öğesinin durumu|  
|---------------------|-----------------------|  
|Noktalı kenarlığı|Öğe bağlantılı|  
|Düz kenarlık|Öğesi, belgeye katıştırılır|  
|Tanıtıcıları yeniden boyutlandırma|Şu anda seçili öğe|  
|Taranmış kenarlığı|Öğe şu anda yerinde etkin olduğu|  
|Tarama deseni yer paylaşımları öğesi|Öğesinin açık sunucusudur|  
  
 Kolayca OLE öğesi durumunu denetler ve uygun stilleri ayarlayan bir yordamı kullanarak bu başlatma işleyebilir. **SetupTracker** OCLIENT örnekte bulunan işlevi İzleyicisi başlatma gösterir. Bu işlev, İzleyici adresini parametreleridir *pTracker*; bir izleyici için ilgili istemci öğesi işaretçi `pItem`; bir dikdörtgen gösteren bir işaretçi *pTrueRect*. Bu işlev daha eksiksiz bir örnek için bkz: MFC OLE örnek [OCLIENT](../visual-cpp-samples.md).  
  
 **SetupTracker** kod örneğinde tek bir işlevi sunar; satırları işlevinin işlev özellikleri tartışması ile interspersed:  
  
 [!code-cpp[NVC_MFCOClient#1](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_1.cpp)]  
  
 İzleyici minimum boyut ayarlama ve İzleyici stilini temizleme başlatıldı.  
  
 [!code-cpp[NVC_MFCOClient#2](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_2.cpp)]  
  
 Aşağıdaki satırları öğe şu anda seçili öğenin veya belgeye bağlı katıştırılmış kontrol edin. Kenarlığın içinde üzerinde bulunan yeniden boyutlandırma öğesi seçili belirten stiline eklenir. Öğe belgenize bağlıysa, noktalı kenarlık stili kullanılır. Öğe eklendiyse düz bir kenarlık kullanılır.  
  
 [!code-cpp[NVC_MFCOClient#3](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_3.cpp)]  
  
 Aşağıdaki kod yer paylaşımları öğe şu anda ise taranmış desenle öğeyi açın.  
  
 [!code-cpp[NVC_MFCOClient#4](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_4.cpp)]  
  
 Görüntülenecek İzleyici sahip olduğunda bu işlev sonra çağırabilirsiniz. Örneğin, bu işlevden çağırma `OnDraw` görünüm sınıfınızın işlevi. Görünümü yeniden çizilmiş olduğunda bu İzleyici'nin Görünüm güncelleştirir. Tam bir örnek için bkz: **CMainView::OnDraw** işlevi MFC OLE örnek [OCLIENT](../visual-cpp-samples.md).  
  
 Uygulamanızda, yeniden boyutlandırma, taşıma veya isabet algılama gibi İzleyicisi kod gerektiren olaylar meydana gelir. Bu Eylemler, genellikle girişiminde alın veya öğeyi taşımak için yapılmakta gösterir. Bu durumlarda, ne gerçekleşti karar vermeniz gerekir: bir yeniden boyutlandırma tutamacını veya bir kısmı arasındaki kenarlığın tanıtıcıları yeniden boyutlandırın. `OnLButtonDown` İleti işleyicisi fareyi öğesi göre konumunu test etmek için iyi bir yerdir. Çağırmaya `CRectTracker::HitTest`. Test yanı sıra bir şey döndürürse **CRectTracker::hitOutside**, yeniden boyutlandırılmış veya taşınmış öğesi değil. Bu nedenle, yapılan bir çağrı olmalısınız `Track` üye işlevi. Bkz: **CMainView::OnLButtonDown** işlevi bulunan MFC OLE örnek [OCLIENT](../visual-cpp-samples.md) tam bir örnek için.  
  
 `CRectTracker` Sınıfı, bir taşıma yeniden boyutlandırmak veya sürükleme işlemi sürüyor yeri belirtmek için kullanılan birkaç farklı imleç şekiller sağlar. Bu olayı işlemek için öğe fare altında şu anda seçili olup olmadığını denetleyin. İse, çağırmaya `CRectTracker::SetCursor`, varsayılan işleyici arayın. MFC OLE örnekten aşağıdaki örnekte olduğu [OCLIENT](../visual-cpp-samples.md):  
  
 [!code-cpp[NVC_MFCOClient#5](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_5.cpp)]  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [İzleyiciler: OLE Uygulamanızda İzleyicileri Uygulama](../mfc/trackers-implementing-trackers-in-your-ole-application.md)

