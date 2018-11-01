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
ms.openlocfilehash: f6774f1de1e7abd318e5cd38fed1a2c805270c15
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443335"
---
# <a name="activation-verbs"></a>Etkinleştirme: Fiiller

Bu makalede rol birincil ve ikincil fiilleri play ole'deki açıklanmaktadır [etkinleştirme](../mfc/activation-cpp.md).

Genellikle, gömülü bir öğe çift düzenlemek kullanıcının sağlar. Ancak, bazı öğeler bu şekilde davranmayabilir. Örneğin, Ses Kaydedicisi uygulama ile oluşturduğunuz bir öğeye çift sunucu ayrı bir pencerede açmaz; Bunun yerine, ses çalar.

Ses Kaydedicisi'ni öğelerin farklı "birincil fiil." bulunduğunu bu davranışı fark sebebi Birincil fiil kullanıcı OLE öğesini tıkladığında gerçekleşen eylemi var. OLE öğeleri çoğu türleri için birincil fiil öğeyi oluşturan sunucu başlatan Düzenle ' dir. Ses Kaydedicisi'ni öğeleri gibi öğeleri bazı türleri birincil fiil Play içindir.

Yalnızca bir fiil türlerde OLE öğeleri destekler ve en yaygın bir düzen olduğunu. Ancak, bazı türleri öğeleri birden çok fiilleri destekler. Örneğin, Ses Kaydedicisi öğeyi destekler, ikincil bir fiili düzenleyin.

Sık kullanılan başka bir fiil, açık olur. Sunucu uygulaması ayrı bir pencerede başlatılan dışında açık fiili düzenleme için aynıdır. Kapsayıcı uygulaması ya da sunucu uygulaması yerinde etkinleştirme desteklemediğinde bu fiili kullanılmalıdır.

Öğe seçildiğinde birincil fiil dışındaki tüm fiiller alt menü komutu aracılığıyla çağrılması gerekir. Bu alt öğe tarafından desteklenen tüm fiiller içerir ve genellikle tarafından ulaşıldığında *typename* **nesne** komutunu **Düzenle** menüsü. Hakkında bilgi için *typename* **nesne** komutu, makaleye göz atın [menüler ve kaynaklar: kapsayıcı ekleme](../mfc/menus-and-resources-container-additions.md).

Windows kayıt defteri veritabanındaki sunucu uygulaması destekler fiilleri listelenir. Sunucu uygulamanızı Microsoft Foundation Class Kitaplığı ile yazılmışsa, sunucu yeniden başlatıldığında, otomatik olarak tüm fiiller kaydeder. Aksi durumda, sunucu uygulamasının başlangıç aşamasında kaydolmalıdır. Daha fazla bilgi için bkz [kayıt](../mfc/registration.md).

## <a name="see-also"></a>Ayrıca Bkz.

[Etkinleştirme](../mfc/activation-cpp.md)<br/>
[Kapsayıcılar](../mfc/containers.md)<br/>
[Sunucular](../mfc/servers.md)

