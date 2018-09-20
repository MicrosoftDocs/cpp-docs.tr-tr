---
title: Üstbilgi öğesi özelleştirme&#39;görünümünü | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- header controls [MFC], customization of items
- CHeaderCtrl class [MFC], customizing the items
- HDS_ styles
ms.assetid: b1e1e326-ec7d-4dbd-a46f-96a3e2055618
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 61c0e3e26679b2b84e3ea18a8e1bb92722d73e22
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46442909"
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

