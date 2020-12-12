---
description: 'Daha fazla bilgi edinin: sunucular: sunucu öğeleri'
title: 'Sunucular: Sunucu Öğeleri'
ms.date: 11/04/2016
helpviewer_keywords:
- server items, implementing
- servers [MFC], server items
- architecture [MFC], server-item
- server items
- OLE server applications [MFC], server items
ms.assetid: 28ba81a1-726a-4728-a52d-68bc7efd5a3c
ms.openlocfilehash: e3fceb3abe89ca6cda432d60441a47fc0d452cfc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217321"
---
# <a name="servers-server-items"></a>Sunucular: Sunucu Öğeleri

Bir kapsayıcı, bir kullanıcının katıştırılmış veya bağlantılı OLE öğesini düzenleyebilmesi için bir sunucu başlattığında, sunucu uygulaması "sunucu öğesi" oluşturur. Öğesinden türetilen bir sınıfın nesnesi olan sunucu öğesi, `COleServerItem` sunucu belgesi ile kapsayıcı uygulaması arasında bir arabirim sağlar.

`COleServerItem`Sınıfı, genellikle kapsayıcıdaki isteklere yanıt olarak OLE tarafından çağrılan birkaç geçersiz kılınabilir üye işlevi tanımlar. Sunucu öğeleri, sunucu belgesinin veya tüm belgenin bir bölümünü temsil edebilir. Bir OLE öğesi kapsayıcı belgeye katıştırıldığında, sunucu öğesi tüm sunucu belgesini temsil eder. OLE öğesi bağlandığında sunucu öğesi, bağlantının bir bölüme mi yoksa tamamına mı ait olduğuna bağlı olarak sunucu belgesinin veya tüm belgenin bir bölümünü temsil edebilir.

[Hiersvr](../overview/visual-cpp-samples.md) örneğinde, örneğin, Server-item sınıfı, `CServerItem` sınıfının bir nesnesine işaretçi olan bir üyeye sahiptir `CServerNode` . `CServerNode`Nesnesi, bir ağaç olan HIERSVR uygulamasının belgesinde bulunan bir düğümdür. `CServerNode`Nesne kök düğüm olduğunda, `CServerItem` nesne tüm belgeyi temsil eder. `CServerNode`Nesne bir alt düğüm olduğunda, `CServerItem` nesnesi belgenin bir parçasını temsil eder. Bu etkileşimin bir örneği için MFC OLE örnek [Hiersvr](../overview/visual-cpp-samples.md) bölümüne bakın.

## <a name="implementing-server-items"></a><a name="_core_implementing_server_items"></a> Sunucu öğelerini uygulama

Uygulamanız için "başlangıç" kodu oluşturmak için uygulama Sihirbazı 'nı kullanırsanız, başlatıcı kodunuzda sunucu öğelerini dahil etmek için yapmanız gerekir, OLE seçenekleri sayfasından sunucu seçeneklerinden birini seçmeniz gerekir. Var olan bir uygulamaya sunucu öğeleri ekliyorsanız, aşağıdaki adımları uygulayın:

#### <a name="to-implement-a-server-item"></a>Sunucu öğesini uygulamak için

1. Sınıfından bir sınıf türet `COleServerItem` .

1. Türetilmiş sınıfınıza üye işlevini geçersiz kılın `OnDraw` .

   Çerçeve, `OnDraw` OLE öğesini bir meta dosyasında işlemek için çağırır. Kapsayıcı uygulaması, öğeyi işlemek için bu meta dosyasını kullanır. Uygulamanızın görünüm sınıfının Ayrıca `OnDraw` , sunucu uygulaması etkinken öğeyi işlemek için kullanılan bir üye işlevi vardır.

1. `OnGetEmbeddedItem`Sunucu belgesi sınıfınız için bir geçersiz kılma uygulayın. Daha fazla bilgi için bkz. [sunucular: sunucu belgelerini uygulama](../mfc/servers-implementing-server-documents.md) ve MFC OLE örnek [hiersvr](../overview/visual-cpp-samples.md).

1. Sunucu öğesi sınıfınızın `OnGetExtent` üye işlevini uygulayın. Framework, öğenin boyutunu almak için bu işlevi çağırır. Varsayılan uygulama hiçbir şey yapmaz.

## <a name="a-tip-for-server-item-architecture"></a><a name="_core_a_tip_for_server.2d.item_architecture"></a> Server-Item mimari için Ipucu

Sunucu [öğelerini uygulama](#_core_implementing_server_items)bölümünde belirtildiği gibi, sunucu uygulamaları hem sunucu görünümünde hem de kapsayıcı uygulaması tarafından kullanılan bir meta dosyasında öğeleri işleyebilmelidir. Microsoft Foundation Class Kitaplığı uygulama mimarisinde, görünüm sınıfının `OnDraw` üye işlevi düzenlenmekte olan öğeyi işler (bkz. [CView:: OnDraw](../mfc/reference/cview-class.md#ondraw) *sınıf kitaplığı başvurusu*). Sunucu öğesi, `OnDraw` öğeyi diğer tüm durumlarda bir meta dosya halinde işler (bkz. [Copaserverıtem:: OnDraw](../mfc/reference/coleserveritem-class.md#ondraw)).

Sunucu-belge sınıfınızda yardımcı işlevler yazarak ve bunları `OnDraw` görünüminizdeki ve sunucu-öğe sınıflarınızda işlevlerden çağırarak kod çoğaltmaktan kaçınabilirsiniz. MFC OLE örnek [Hiersvr](../overview/visual-cpp-samples.md) bu stratejiyi kullanır: bir `CServerView::OnDraw` `CServerItem::OnDraw` `CServerDoc::DrawTree` öğeyi işlemek için işlevler ve her iki çağrı.

Görünüm ve öğenin her ikisi de `OnDraw` farklı koşullarda çiztiğinden üye işlevleri vardır. Görünüm, kaydırma çubukları gibi yakınlaştırma, seçim boyutu ve uzatma, kırpma ve Kullanıcı arabirimi öğeleri gibi etkenlere karşı hesaba sahip olmalıdır. Diğer yandan sunucu öğesi, her zaman OLE nesnesinin tamamını çizer.

Daha fazla bilgi için, bkz. [CView:: OnDraw](../mfc/reference/cview-class.md#ondraw), [copaserverıtem](../mfc/reference/coleserveritem-class.md), [Copaserverıtem:: OnDraw](../mfc/reference/coleserveritem-class.md#ondraw)ve *sınıf kitaplığı başvurusunda* [Cotaserverdoc:: OnGetEmbeddedItem](../mfc/reference/coleserverdoc-class.md#ongetembeddeditem) .

## <a name="see-also"></a>Ayrıca bkz.

[Sunucular](../mfc/servers.md)
