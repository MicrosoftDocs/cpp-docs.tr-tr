---
title: 'Kapsayıcılar: İstemci Öğesi Durumları'
ms.date: 11/04/2016
helpviewer_keywords:
- OLE containers [MFC], client-item states
- states, OLE container client-item
- lifetime, lifetime states and OLE container client items
- client items and OLE containers
ms.assetid: e7021caa-bd07-4adb-976e-f5f3d025bc53
ms.openlocfilehash: 660b544a0f061ae2e4435777cdd934367f2e7652
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87228654"
---
# <a name="containers-client-item-states"></a>Kapsayıcılar: İstemci Öğesi Durumları

Bu makalede, bir istemci öğesinin ömrü boyunca geçtiği farklı durumlar açıklanır.

Bir istemci öğesi, oluşturma, etkinleştirme, değiştirme ve kaydetme gibi birçok durumdan geçer. Öğenin durumu her değiştiğinde Framework, **OLE_CHANGED_STATE** bildirimi Ile [Cotaclientidıtem:: OnChange](reference/coleclientitem-class.md#onchange) öğesini çağırır. İkinci parametre, `COleClientItem::ItemState` Numaralandırmadaki bir değerdir. Aşağıdakilerden biri olabilir:

- *Colet Clientıtem:: emptyState*

- *Colet Clientıtem:: loadedState*

- *Colet Clientıtem:: openState*

- *Colet Clientıtem:: activeState*

- *Colet Clientıtem:: activeUIState*

Boş durumda, bir istemci öğesi henüz tamamen bir öğe değildir. Bellek için ayrılan bellek, ancak henüz OLE öğesinin verileriyle başlatılmamış. Bu, bir istemci öğesinin, öğesine yapılan bir çağrı aracılığıyla oluşturulduğu ve **`new`** tipik iki adımlı oluşturmanın ikinci adımını henüz yaptığı durumdur.

Bir `COleClientItem::CreateFromFile` veya başka bir xxxx işlevi çağrısıyla gerçekleştirilen ikinci adımda `CreateFrom` *xxxx* , öğe tamamen oluşturulur. OLE verileri (bir dosyadan veya pano gibi başka bir kaynaktan) `COleClientItem` türetilmiş nesneyle ilişkili. Artık öğe yüklü durumda.

Bir öğe, kapsayıcının belgesinde yerine, sunucunun penceresinde açıldığında açık (veya tamamen açık) durumda olur. Bu durumda, bir çapraz tarama genellikle öğenin başka bir yerde etkin olduğunu göstermek için kapsayıcının penceresindeki öğenin gösterimine çizilir.

Bir öğe yerinde etkinleştirildiğinde, genellikle etkin durum aracılığıyla yalnızca kısa bir süre geçirir. Daha sonra, sunucunun menülerini, araç çubuklarını ve diğer Kullanıcı Arabirimi bileşenlerini kapsayıcdakilerle birleştirdiğini belirten UI etkin durumuna girer. Bu Kullanıcı arabirimi bileşenlerinin varlığı, UI etkin durumunu etkin durumdan ayırır. Aksi halde etkin durum, UI etkin durumuna benzer. Sunucu geri almayı destekliyorsa, sunucu, yüklenen ya da açık duruma ulaşıncaya kadar OLE öğesinin geri alma durumu bilgilerini korumayı gerektirir.

## <a name="see-also"></a>Ayrıca bkz.

[Kapsayıcılar](containers.md)<br/>
[Etkinleştirme](activation-cpp.md)<br/>
[Kapsayıcılar: Istemci öğesi bildirimleri](containers-client-item-notifications.md)<br/>
[İzleyiciler](trackers.md)<br/>
[CRectTracker sınıfı](reference/crecttracker-class.md)
