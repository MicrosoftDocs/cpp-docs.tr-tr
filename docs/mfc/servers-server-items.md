---
title: 'Sunucular: Sunucu öğeleri'
ms.date: 11/04/2016
helpviewer_keywords:
- server items, implementing
- servers [MFC], server items
- architecture [MFC], server-item
- server items
- OLE server applications [MFC], server items
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
ms.openlocfilehash: abee619aa921b3e036a2bbeb1b4f5ae08d83f5bb
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767905"
---
# <a name="servers-server-items"></a>Sunucular: Sunucu öğeleri

Bir kapsayıcı, bir kullanıcı bir gömülü veya bağlantılı OLE öğesi düzenleyebilmesi bir sunucu başlattığında, sunucu uygulaması bir "sunucu öğesi." oluşturur. Türetilen bir sınıfın bir nesnesi olan sunucu öğesi `COleServerItem`, sunucu belgesi ve kapsayıcı uygulaması arasında bir arabirim sağlar.

`COleServerItem` Sınıfı OLE tarafından genellikle isteklerine yanıt kapsayıcısından çağrılan birden fazla geçersiz kılınabilir üye işlevleri tanımlar. Sunucu öğeleri, sunucu belgesi veya tüm belgeyi bir parçası temsil edebilir. OLE öğesini kapsayıcı belgeye katıştırıldığında, sunucu öğesi tüm sunucu belgeyi temsil eder. OLE öğesini bağlandığında, sunucu öğesi sunucu belgesinin veya bir bölümünü veya tamamını bağlantısı olmasına bağlı olarak tüm belgeyi bir parçası temsil edebilir.

İçinde [HIERSVR](../overview/visual-cpp-samples.md) , örneğin, server-Item sınıfı örneği `CServerItem`, bir sınıfın nesne işaretçisidir üyenin `CServerNode`. `CServerNode` Bir düğüm bir ağaç mı HIERSVR uygulamanın belgedeki bir nesnedir. Zaman `CServerNode` nesnedir kök düğümü `CServerItem` nesne tüm belgeyi temsil eder. Zaman `CServerNode` nesnesi olan bir alt düğüm `CServerItem` nesne belgenin bir bölümünü temsil eder. MFC OLE örnek görmek [HIERSVR](../overview/visual-cpp-samples.md) Bu etkileşim ilişkin bir örnek.

##  <a name="_core_implementing_server_items"></a> Uygulama sunucu öğeleri

Uygulamanız için "Başlangıç" kod üretmek için Uygulama Sihirbazı'nı kullanırsanız, başlangıç kodunuzda sunucu öğeleri eklemek için yapmanız gereken tek şey OLE Seçenekler sayfasından sunucu seçenekleri birini seçmeniz. Sunucu öğeleri mevcut bir uygulamaya ekliyorsanız, aşağıdaki adımları gerçekleştirin:

#### <a name="to-implement-a-server-item"></a>Bir sunucu öğesi uygulamak için

1. Öğesinden bir sınıf türetin `COleServerItem`.

1. Türetilmiş sınıfınızda geçersiz kılmanız `OnDraw` üye işlevi.

   Framework çağrıları `OnDraw` OLE öğesini bir meta dosyasında işlemek için. Kapsayıcı uygulamasını bu meta öğesi işlemek için kullanır. Ayrıca, uygulamanızın görünüm sınıfı olan bir `OnDraw` sunucu uygulamasının etkin olduğunda, öğe işlemek için kullanılan üye işlevi.

1. Geçersiz kılma uygulama `OnGetEmbeddedItem` sunucu belgesinin sınıfınız için. Daha fazla bilgi için bkz [sunucuları: Sunucu belgeleri uygulama](../mfc/servers-implementing-server-documents.md) ve MFC OLE örnek [HIERSVR](../overview/visual-cpp-samples.md).

1. Sunucu öğesi sınıfınızın uygulamak `OnGetExtent` üye işlevi. Framework öğenin boyutunu almak için bu işlevi çağırır. Varsayılan uygulama, hiçbir şey yapmaz.

##  <a name="_core_a_tip_for_server.2d.item_architecture"></a> Sunucu öğesi mimarisine yönelik bir ipucu

Belirtilen [uygulama sunucu öğeleri](#_core_implementing_server_items), sunucu uygulamaları sunucu görünümü hem de kapsayıcı uygulama tarafından kullanılan bir meta dosyası öğeleri işleme olanağına olmalıdır. Microsoft Foundation Class Kitaplığı'nın uygulama mimarisinin, görünüm sınıfı içinde `OnDraw` üye işlevi, düzenlenirken öğesi işler (bkz [CView::OnDraw](../mfc/reference/cview-class.md#ondraw) içinde *sınıf kitaplığı başvurusu* ). Sunucu öğenin `OnDraw` diğer tüm durumlarda bir meta dosyası içine bir öğe işler (bkz [COleServerItem::OnDraw](../mfc/reference/coleserveritem-class.md#ondraw)).

Sunucu belgesinin sınıfınızda yardımcı işlevler yazma ve bunları çağırma kodunun çoğaltma kaçınabilirsiniz `OnDraw` , Görünüm ve sunucu öğesi sınıflardaki işlevleri. MFC OLE örnek [HIERSVR](../overview/visual-cpp-samples.md) bu strateji kullanır: işlevleri `CServerView::OnDraw` ve `CServerItem::OnDraw` çağırın `CServerDoc::DrawTree` öğesini işlemek için.

Görünüm ve öğe `OnDraw` üye işlevleri, çünkü bunlar farklı koşullar altında çizin. Görünüm gibi yakınlaştırma, seçim boyutunu ve uzantı, kırpma ve kaydırma çubukları gibi kullanıcı arabirimi öğeleri olarak dikkate dikkate almanız gerekir. Sunucu öğesi, diğer yandan, her zaman tüm OLE nesnesi çizer.

Daha fazla bilgi için [CView::OnDraw](../mfc/reference/cview-class.md#ondraw), [Coleserverıtem](../mfc/reference/coleserveritem-class.md), [COleServerItem::OnDraw](../mfc/reference/coleserveritem-class.md#ondraw), ve [COleServerDoc::OnGetEmbeddedItem](../mfc/reference/coleserverdoc-class.md#ongetembeddeditem)içinde *sınıf kitaplığı başvurusu*.

## <a name="see-also"></a>Ayrıca bkz.

[Sunucular](../mfc/servers.md)
