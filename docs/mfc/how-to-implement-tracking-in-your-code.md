---
description: ': Nasıl yapılır: kodunuzda Izleme uygulama hakkında daha fazla bilgi edinin'
title: 'Nasıl yapılır: Kodunuzda İzleme Uygulama'
ms.date: 11/04/2016
helpviewer_keywords:
- CRectTracker class [MFC], implementing trackers
ms.assetid: baaeca2c-5114-485f-bf58-8807db1bc973
ms.openlocfilehash: 1b9211978c6ba5169a2d55e272b7e3ddf0678fd6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330202"
---
# <a name="how-to-implement-tracking-in-your-code"></a>Nasıl yapılır: Kodunuzda İzleme Uygulama

Bir OLE öğesini izlemek için öğe ile ilgili belirli olayları (öğeyi tıklatmak veya belge görünümünü güncelleştirmek) işlemeniz gerekir. Her durumda, geçici bir [CRectTracker](reference/crecttracker-class.md) nesnesi bildirmek ve öğeyi bu nesnenin yoluyla işlemek yeterlidir.

Bir Kullanıcı bir öğe seçtiğinde veya bir menü komutuyla bir nesne eklediğinde, OLE öğesinin durumunu göstermek için izleyici 'yi uygun stillerle başlatmalısınız. Aşağıdaki tabloda OCLIENT örneği tarafından kullanılan kurallar özetlenmektedir. Bu stiller hakkında daha fazla bilgi için bkz `CRectTracker` ..

### <a name="container-styles-and-states-of-the-ole-item"></a>OLE öğesinin kapsayıcı stilleri ve durumları

|Stil görüntülendi|OLE öğesinin durumu|
|---------------------|-----------------------|
|Noktalı kenarlık|Öğe bağlı|
|Düz kenarlık|Öğe belgenize eklenmiş|
|Yeniden boyutlandırma tutamaçları|Öğe şu anda seçili|
|Taranmış kenarlık|Öğe şu anda yerinde etkin|
|Tarama deseninin yer paylaşımı öğesi|Öğenin sunucusu açık|

Bu başlatmayı OLE öğesinin durumunu denetleyen ve uygun stilleri ayarlayan bir yordam kullanarak kolayca işleyebilirsiniz. `SetupTracker`OCLIENT örneğinde bulunan işlevi izleyici başlatmasını gösterir. Bu işlevin parametreleri, izleyici 'nin adresidir, *pTracker*; izleyici, *Pitem*; ile ilgili istemci öğesine yönelik bir işaretçi ve bir dikdörtgen işaretçisi, *pTrueRect*. Bu işlevin daha kapsamlı bir örneği için bkz. MFC OLE örnek [Oclient](../overview/visual-cpp-samples.md).

**SetupTracker** kod örneği tek bir işlev gösterir; işlevin satırları işlevin özelliklerinin tartışmasına göre yapılır:

[!code-cpp[NVC_MFCOClient#1](codesnippet/cpp/how-to-implement-tracking-in-your-code_1.cpp)]

İzleyici, en küçük boyut ayarlanarak ve izleyici stilini temizleyerek başlatılır.

[!code-cpp[NVC_MFCOClient#2](codesnippet/cpp/how-to-implement-tracking-in-your-code_2.cpp)]

Aşağıdaki satırlar, öğenin şu anda seçili olup olmadığını ve öğenin belgeye bağlanıp bağlanmadığını ve bu öğeye gömülü olduğunu denetler. Kenarlığın içinde bulunan yeniden boyutlandırma tutamaçları, öğenin şu anda seçili olduğunu belirten stile eklenir. Öğe belgenize bağlıysa, noktalı kenarlık stili kullanılır. Öğe katıştırılmışsa, düz bir kenarlık kullanılır.

[!code-cpp[NVC_MFCOClient#3](codesnippet/cpp/how-to-implement-tracking-in-your-code_3.cpp)]

Aşağıdaki kod, öğe şu anda açıksa, öğe bir hagesle birlikte yer açar.

[!code-cpp[NVC_MFCOClient#4](codesnippet/cpp/how-to-implement-tracking-in-your-code_4.cpp)]

Daha sonra izleyici her görüntülendiğinde bu işlevi çağırabilirsiniz. Örneğin, bu işlevi `OnDraw` Görünüm sınıfınızın işlevinden çağırın. Bu, görünüm yeniden boyandiğinde izleyici görünümünü güncelleştirir. Tüm örnek için, `CMainView::OnDraw` MFC OLE örnek [oclient](../overview/visual-cpp-samples.md)işlevine bakın.

Uygulamanızda, yeniden boyutlandırma, taşıma veya isabet algılama gibi izleyici kodu gerektiren olaylar meydana gelir. Bu eylemler genellikle öğeyi almak veya taşımak için bir deneme yapıldığını gösterir. Bu gibi durumlarda, nelerin boyutlandırılacağını belirlemeniz gerekir: bir yeniden boyutlandırma tutamacı veya yeniden boyutlandırma tutamaçları arasındaki kenarlığın bir bölümü. `OnLButtonDown`İleti işleyicisi, fare konumunu öğeyle bağlantılı olarak test etmek için uygun bir yerdir. İçin bir çağrısı yapın `CRectTracker::HitTest` . Test bir şeyi geri döndürürse `CRectTracker::hitOutside` , öğe yeniden boyutlandırılıyor veya taşınıyor. Bu nedenle, üye işlevine bir çağrı yapmanız gerekir `Track` . `CMainView::OnLButtonDown`Tüm örnek IÇIN MFC OLE örnek [oclient](../overview/visual-cpp-samples.md) içinde bulunan işleve bakın.

`CRectTracker`Sınıfı, bir taşıma, yeniden boyutlandırma veya sürükleme işleminin yapılıp yapılmayacağını göstermek için kullanılan birkaç farklı imleç şekli sağlar. Bu olayı işlemek için, fare altında bulunan öğenin seçili olup olmadığını denetleyin. Varsa, için bir çağrı yapın `CRectTracker::SetCursor` veya varsayılan işleyiciyi çağırın. Aşağıdaki örnek MFC OLE örnek [Oclient](../overview/visual-cpp-samples.md)örneğidir:

[!code-cpp[NVC_MFCOClient#5](codesnippet/cpp/how-to-implement-tracking-in-your-code_5.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[İzleyiciler: OLE uygulamanızda Izleyicileri uygulama](trackers-implementing-trackers-in-your-ole-application.md)
