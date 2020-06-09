---
title: 'Etkinleştirme: Fiiller'
ms.date: 11/04/2016
helpviewer_keywords:
- verbs [MFC]
- OLE [MFC], activation
- edit verb [MFC]
- activation [MFC], verbs
- OLE [MFC], editing
- Primary verb [MFC]
- OLE activation {MFC]
ms.assetid: eb56ff23-1de8-43ad-abeb-dc7346ba7b70
ms.openlocfilehash: 03edba0a4336fdc147ef6dd10c7a8154aca19d3a
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616638"
---
# <a name="activation-verbs"></a>Etkinleştirme: Fiiller

Bu makalede, birincil ve ikincil fiillerin OLE [etkinleştirmede](activation-cpp.md)oynamakta olduğu rol açıklanmaktadır.

Genellikle, katıştırılmış bir öğeye çift tıklamak kullanıcının onu düzenlemesini sağlar. Ancak, bazı öğeler bu şekilde davranmaz. Örneğin, Ses Kaydedicisi uygulamasıyla oluşturulan bir öğeye çift tıklamak sunucuyu ayrı bir pencerede açmaz; Bunun yerine, sesi çalar.

Bu davranış farkının nedeni, Ses Kaydedicisi öğelerinin farklı bir "birincil fiil" olmasının nedenidir. Birincil fiil, Kullanıcı bir OLE öğesine çift tıkladığında gerçekleştirilen eylemdir. Çoğu OLE öğesi türü için, birincil fiil, öğeyi oluşturan sunucuyu başlatan Düzenle ' dir. Ses Kaydedicisi öğeleri gibi bazı tür öğeler için birincil fiil oynatılır.

Birçok OLE öğesi türü, yalnızca bir fiil destekler ve en sık kullanılan bir düzenlemedir. Ancak bazı öğe türleri birden çok fiil destekler. Örneğin, Ses Kaydedicisi öğeleri, ikincil fiil olarak düzenlemeyi destekler.

Sık kullanılan başka bir fiil de açıktır. Açık fiil, sunucu uygulamasının ayrı bir pencerede başlatılmasının dışında, Düzenle ile aynıdır. Bu fiil, kapsayıcı uygulaması veya sunucu uygulaması yerinde etkinleştirmeyi desteklemediği zaman kullanılmalıdır.

Öğe seçildiğinde, birincil fiil dışındaki tüm fiillerin bir alt menü komutuyla çağrılması gerekir. Bu alt menü, öğe tarafından desteklenen tüm fiilleri içerir ve genellikle **düzenleme** menüsünde *TypeName* **nesne** komutu tarafından verilir. *TypeName* **nesnesi** komutu hakkında daha fazla bilgi Için, [menüler ve kaynaklar: kapsayıcı eklemeleri](menus-and-resources-container-additions.md)makalesine bakın.

Sunucu uygulamasının desteklediği fiiller Windows kayıt veritabanında listelenir. Sunucu uygulamanız Microsoft Foundation Class Kitaplığı yazılmışsa, sunucu başlatıldığında otomatik olarak tüm fiiller kaydedilir. Aksi takdirde, bunları sunucu uygulamasının başlatma aşamasında kaydetmeniz gerekir. Daha fazla bilgi için bkz. Makale [kaydı](registration.md).

## <a name="see-also"></a>Ayrıca bkz.

[Etkinleştirme](activation-cpp.md)<br/>
[Kapsayıcılar](containers.md)<br/>
[Sunucular](servers.md)
