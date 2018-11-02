---
title: Üstbilgi öğesi özelleştirme&#39;görünümünü
ms.date: 11/04/2016
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
ms.openlocfilehash: 8610a3fcc489e69d95f0b0d2e78987664130555e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50511027"
---
# <a name="customizing-the-header-item39s-appearance"></a>Üstbilgi öğesi özelleştirme&#39;görünümünü

Ayarlayarak *dwStyle* parametre bir üst bilgi denetiminin ilk oluşturduğunuzda ([CHeaderCtrl::Create](../mfc/reference/cheaderctrl-class.md#create)), görünüm tanımlayabilirsiniz ve üst bilgisi davranışını öğelerini ya da kendi üst denetim.

Ayarlayabileceğiniz stilleri ve bunların amacı bazıları aşağıda verilmiştir:

- Bir basma düğmesi gibi ara bir üst öğe yapma **HDS_BUTTONS** stili.

   Microsoft Outlook içinde olduğu gibi verileri belirli bir sütuna göre sıralama gibi bir üst öğe üzerinde fare tıklamalara yanıt eylemleri gerçekleştirmek istiyorsanız bu stil kullanın.

- Fare imlecini geçerken üstbilgi öğeleri "sıcak takibi" görünümü vermek için kullanın **HDS_HOTTRACK** stili.

   İşaretçiyi bir öğe yoksa düz üzerinden geçerken sıcak takibi görüntüler 3B anahat çubuğu.

- Üstbilgi denetimi gizlenmelidir belirtmek için kullanın **HDS_HIDDEN** stili.

   **HDS_HIDDEN** stilini gösterir üstbilgi denetimi veri kapsayıcısını ve görsel bir denetim kullanılmak üzere tasarlanmıştır. Bu stil denetimi otomatik olarak gizlemek olmayan, ancak bunun yerine, davranışını etkileyen `CHeaderCtrl::Layout`. Döndürülen değer *cy* üyesi `WINDOWPOS` yapısı, sıfır olacaktır gösteren denetimi kullanıcıya görünür olmamalıdır.

Bu özellikler hakkında daha fazla bilgi için bkz. [öğeleri](/windows/desktop/Controls/header-controls) Windows SDK. Üstbilgi denetimine öğe ekleme hakkında daha fazla bilgi için bkz: [üstbilgi denetimine öğe eklemeyi](../mfc/adding-items-to-the-header-control.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

