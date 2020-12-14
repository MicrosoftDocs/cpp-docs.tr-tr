---
description: 'Hakkında daha fazla bilgi edinin: CToolTipCtrl kullanarak bir CToolTipCtrl nesnesi oluşturma ve Işleme'
title: CToolTipCtrl Kullanarak bir CToolTipCtrl Nesnesi Oluşturma ve Düzenleme
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], creating
- CToolTipCtrl class [MFC], using
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
ms.openlocfilehash: 363d46ce078b71cf88d742ae390ab674a73ab935
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202346"
---
# <a name="using-ctooltipctrl-to-create-and-manipulate-a-ctooltipctrl-object"></a>CToolTipCtrl Kullanarak bir CToolTipCtrl Nesnesi Oluşturma ve Düzenleme

İşte [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) kullanımı örneği:

### <a name="to-create-and-manipulate-a-ctooltipctrl"></a>Bir CToolTipCtrl oluşturmak ve değiştirmek için

1. Nesnesini oluşturun `CToolTipCtrl` .

1. Windows araç ipucu ortak denetimini oluşturmak ve nesneye eklemek için [Oluştur](../mfc/reference/ctooltipctrl-class.md#create) ' a çağrı yapın `CToolTipCtrl` .

1. Araç ipucu denetimi ile bir araç kaydetmek için [AddTool](../mfc/reference/ctooltipctrl-class.md#addtool) çağırın. böylece araç ipucunda depolanan bilgiler imleç araç üzerindeyken görüntülenir.

1. Araç ipucunun bir araç için sakladığı bilgileri ayarlamak için [SetToolInfo](../mfc/reference/ctooltipctrl-class.md#settoolinfo) çağırın.

1. Araç için yeni bir sınırlayıcı dikdörtgen ayarlamak üzere [SetToolRect](../mfc/reference/ctooltipctrl-class.md#settoolrect) çağrısı yapın.

1. Verilen aracın sınırlayıcı dikdörtgeni içinde olup olmadığını belirleme noktasını test etmek için [Ittest](../mfc/reference/ctooltipctrl-class.md#hittest) çağırın ve bu durumda araç hakkında bilgi alın.

1. Araç ipucu denetimine kayıtlı araçların sayısını almak için [GetToolCount](../mfc/reference/ctooltipctrl-class.md#gettoolcount) çağrısı yapın.

## <a name="see-also"></a>Ayrıca bkz.

[CToolTipCtrl Kullanma](../mfc/using-ctooltipctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
