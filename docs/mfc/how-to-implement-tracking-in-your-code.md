---
title: 'Nasıl yapılır: Kodunuzda İzleme Uygulama'
ms.date: 11/04/2016
helpviewer_keywords:
- CRectTracker class [MFC], implementing trackers
ms.assetid: baaeca2c-5114-485f-bf58-8807db1bc973
ms.openlocfilehash: 0a6a8313c02566c4d1cde82b288b42e150651b02
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50428697"
---
# <a name="how-to-implement-tracking-in-your-code"></a>Nasıl yapılır: Kodunuzda İzleme Uygulama

OLE öğesini izlemek için öğeye tıklandığında veya belgenin görünümünü güncelleştirme gibi öğesine ilgili belirli olayları işlemesi gerekir. Her durumda, geçici bir bildirmek yeterli [CRectTracker](../mfc/reference/crecttracker-class.md) yoluyla bu nesnesi nesne ve öğe.

Bir kullanıcı bir öğeyi seçer veya bir menü komutu ile bir nesne ekler OLE öğesinin durumunu göstermek için uygun stilleri izleyiciyle başlatmanız gerekir. Aşağıdaki tabloda OCLIENT örnek tarafından kullanılan kuralları açıklar. Bu stiller hakkında daha fazla bilgi için bkz. `CRectTracker`.

### <a name="container-styles-and-states-of-the-ole-item"></a>Kapsayıcı stilleri ve OLE öğesinin durumları

|Görüntülenen stili|OLE öğesinin durumu|
|---------------------|-----------------------|
|Noktalı kenarlığı|Öğesi bağlandı|
|Düz kenarlık|Öğesi, belgeye eklenir|
|Yeniden boyutlandırma tutamaçları|Şu anda seçili öğe|
|Taranmış kenarlık|Öğe şu anda yerinde etkin olduğu|
|Tarama desen yer paylaşımları öğesi|Öğenin sunucu Aç|

OLE öğesi durumunu denetler ve uygun stilleri ayarlayan bir yordamı kullanarak kolayca bu başlatma başa çıkabilir. `SetupTracker` OCLIENT örnekte bulunan işlevi İzleyicisi başlatma gösterir. Bu işlev, İzleyici adresini parametreleridir *pTracker*; bir alt İzleyici için ilgili istemci öğesi işaretçisi *pItem*; ve bir dikdörtgen bir işaretçiye *pTrueRect* . Bu işlevin daha eksiksiz bir örnek için bkz. MFC OLE örnek [OCLIENT](../visual-cpp-samples.md).

**SetupTracker** kod örneği, tek bir işlev sunar; işlev satırlarını tartışma işlevin özellikleri ile interspersed:

[!code-cpp[NVC_MFCOClient#1](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_1.cpp)]

İzleyici, en düşük boyut ayarlama ve temizleme İzleyici stilini başlatılır.

[!code-cpp[NVC_MFCOClient#2](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_2.cpp)]

Aşağıdaki satırları öğe şu anda seçili olduğundan ve öğe belgeye bağlantılı veya katıştırılmış olup olmadığını kontrol edin. Yeniden boyutlandırma tutamaçları üzerinde kenarlığı içinde bulunan öğesi seçili belirten stiline eklenir. Öğe belgenize bağlıysa, noktalı kenarlık stili kullanılır. Öğe eklendiyse düz bir kenarlık kullanılır.

[!code-cpp[NVC_MFCOClient#3](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_3.cpp)]

Aşağıdaki kod paylaşımı öğe öğe şu anda ise taranmış bir desen ile açın.

[!code-cpp[NVC_MFCOClient#4](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_4.cpp)]

İzleyici görüntülenecek olduğunda daha sonra bu işlevi çağırabilirsiniz. Örneğin, bu işlevden çağırma `OnDraw` işlevi, görünüm sınıfı. Görünümü yeniden çizilmesini olduğunda bu İzleyici'nın görünümünü güncelleştirir. Tam bir örnek için bkz. `CMainView::OnDraw` MFC OLE örnek işlevi [OCLIENT](../visual-cpp-samples.md).

Uygulamanızda, yeniden boyutlandırma, taşıma veya isabet algılama gibi İzleyicisi kod gerektiren olayları ortaya çıkar. Bu Eylemler, genellikle girişiminde alın veya öğeyi taşı için yapılan gösterir. Bu gibi durumlarda, ne yakaladı karar vermeniz gerekir: bir yeniden boyutlandırma tutamacı ya da bir kısmını arasındaki kenarlığın yeniden boyutlandırma tutamaçları. `OnLButtonDown` İleti işleyicisi öğesi ile ilgili olarak farenin konumunun test etmek için iyi bir yerdir. Çağrı yapmak `CRectTracker::HitTest`. Test yanı sıra bir şey döndürürse `CRectTracker::hitOutside`, öğeyi yeniden boyutlandırılabilir veya taşınmış olan. Bu nedenle, çağrı yapmak `Track` üye işlevi. Bkz: `CMainView::OnLButtonDown` işlevi MFC OLE örnekte bulunan [OCLIENT](../visual-cpp-samples.md) tam bir örnek.

`CRectTracker` Sınıfı bir taşıma, yeniden boyutlandırmak veya sürükleyin işlemi sürüyor yeri belirtmek için kullanılan birkaç farklı işaretçi şekilleri sağlar. Bu olayı işlemek için öğe fareyi altında şu anda seçili olup olmadığını denetleyin. İse, çağrı yapmak `CRectTracker::SetCursor`, veya varsayılan işleyici arayın. Aşağıdaki örnek, MFC OLE örnekten [OCLIENT](../visual-cpp-samples.md):

[!code-cpp[NVC_MFCOClient#5](../mfc/codesnippet/cpp/how-to-implement-tracking-in-your-code_5.cpp)]

## <a name="see-also"></a>Ayrıca Bkz.

[İzleyiciler: OLE Uygulamanızda İzleyicileri Uygulama](../mfc/trackers-implementing-trackers-in-your-ole-application.md)

