---
title: 'Sunucular: Sunucu Öğeleri'
ms.date: 11/04/2016
helpviewer_keywords:
- server items, implementing
- servers [MFC], server items
- architecture [MFC], server-item
- server items
- OLE server applications [MFC], server items
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
ms.openlocfilehash: 8ae24104a30a0b44e92b889006907911124310f7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81355107"
---
# <a name="servers-server-items"></a>Sunucular: Sunucu Öğeleri

Bir kapsayıcı, kullanıcının katıştırılmış veya bağlantılı bir OLE öğesini düzenlemesi için bir sunucu başlattığında, sunucu uygulaması bir "sunucu öğesi" oluşturur. Türetilen bir sınıfın nesnesi olan `COleServerItem`sunucu öğesi, sunucu belgesi ile kapsayıcı uygulaması arasında bir arabirim sağlar.

Sınıf, `COleServerItem` genellikle kapsayıcıdan gelen isteklere yanıt olarak OLE tarafından çağrılan birkaç geçersiz üye işlev tanımlar. Sunucu öğeleri sunucu belgesinin bir kısmını veya belgenin tamamını temsil edebilir. Bir OLE öğesi kapsayıcı belgeye katıştırıldığında, sunucu öğesi sunucu belgesinin tamamını temsil eder. OLE öğesi bağlandığında, sunucu öğesi bağlantının bir parçaya mı yoksa bütüne mi olduğuna bağlı olarak sunucu belgesinin bir bölümünü veya belgenin tamamını temsil edebilir.

[HIERSVR](../overview/visual-cpp-samples.md) örneğin, sunucu öğesi sınıfı, `CServerItem`sınıfın bir nesneye işaretçi bir üyesi `CServerNode`vardır. Nesne, `CServerNode` HIERSVR uygulamasının bir ağaç olan belgesindeki bir düğümdür. `CServerNode` Nesne kök düğüm olduğunda, `CServerItem` nesne belgenin tamamını temsil eder. `CServerNode` Nesne bir alt düğüm olduğunda, `CServerItem` nesne belgenin bir bölümünü temsil eder. Bu etkileşimin bir örneği için MFC OLE örnek [HIERSVR'a](../overview/visual-cpp-samples.md) bakın.

## <a name="implementing-server-items"></a><a name="_core_implementing_server_items"></a>Sunucu Öğelerini Uygulama

Uygulamanız için "başlatıcı" kodu oluşturmak için uygulama sihirbazını kullanıyorsanız, başlangıç kodunuza sunucu öğelerieklemek için yapmanız gereken tek şey OLE Seçenekleri sayfasından sunucu seçeneklerinden birini seçmektir. Varolan bir uygulamaya sunucu öğeleri ekliyorsanız, aşağıdaki adımları gerçekleştirin:

#### <a name="to-implement-a-server-item"></a>Bir sunucu öğesini uygulamak için

1. Bir sınıf türetmek `COleServerItem`.

1. Türemiş `OnDraw` sınıfınızda, üye işlevi geçersiz kılın.

   Çerçeve, `OnDraw` OLE öğesini bir metadosyaya dönüştürmeyi çağırır. Kapsayıcı uygulaması öğeyi işlemek için bu metadosyayı kullanır. Uygulamanızın görünüm sınıfı, sunucu `OnDraw` uygulaması etkin olduğunda öğeyi işlemek için kullanılan bir üye işlevi de vardır.

1. Sunucu belge sınıfınız `OnGetEmbeddedItem` için geçersiz kılma uygulayın. Daha fazla bilgi için, makale [Sunucular bakın: Sunucu Belgeleri](../mfc/servers-implementing-server-documents.md) ve MFC OLE örnek [HIERSVR](../overview/visual-cpp-samples.md)uygulanması.

1. Sunucu öğesi sınıfının `OnGetExtent` üye işlevini uygulayın. Çerçeve, öğenin boyutunu almak için bu işlevi çağırır. Varsayılan uygulama hiçbir şey yapmaz.

## <a name="a-tip-for-server-item-architecture"></a><a name="_core_a_tip_for_server.2d.item_architecture"></a>Sunucu-Öğe Mimarisi için İpucu

[Sunucu Öğelerinin Uygulanmasında](#_core_implementing_server_items)belirtildiği gibi, sunucu uygulamaları öğeleri hem sunucu görünümünde hem de kapsayıcı uygulaması tarafından kullanılan bir metadosyada işleyebilmelidir. Microsoft Hazırlık Sınıfı Kitaplığı'nın uygulama mimarisinde, `OnDraw` görünüm sınıfının üye işlevi öğeyi düzenlenirken işler (bkz. [CView:OnDraw](../mfc/reference/cview-class.md#ondraw) in the *Class Library Reference).* Sunucu öğesi, `OnDraw` öğeyi diğer tüm durumlarda bir metadosyaya dönüştürür (bkz. [COleServerItem:OnDraw).](../mfc/reference/coleserveritem-class.md#ondraw)

Sunucu belge sınıfınızda yardımcı işlevleri yazıp görünümünizdeki ve sunucu öğesi sınıflarınızdaki `OnDraw` işlevlerden çağırarak kodun çoğaltılmasını önleyebilirsiniz. MFC OLE örnek [HIERSVR](../overview/visual-cpp-samples.md) bu stratejiyi kullanır: işlevleri `CServerView::OnDraw` ve `CServerItem::OnDraw` her ikisi de öğeyi işlemek için çağrı. `CServerDoc::DrawTree`

Farklı koşullar altında çizmek `OnDraw` çünkü görünüm ve öğenin her ikisi de üye işlevleri vardır. Görünüm, yakınlaştırma, seçim boyutu ve kapsamı, kırpma ve kaydırma çubukları gibi kullanıcı arabirimi öğeleri gibi faktörleri dikkate almalıdır. Sunucu öğesi, diğer taraftan, her zaman tüm OLE nesnesini çizer.

Daha fazla bilgi için [Bkz. CView::OnDraw](../mfc/reference/cview-class.md#ondraw), COleServerItem , [COleServerItem::OnDraw](../mfc/reference/coleserveritem-class.md#ondraw), ve [COleServerDoc::OnGetEmbeddedItem](../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) *Sınıf Kitaplığı Referans*. [COleServerItem](../mfc/reference/coleserveritem-class.md)

## <a name="see-also"></a>Ayrıca bkz.

[Sunucular](../mfc/servers.md)
