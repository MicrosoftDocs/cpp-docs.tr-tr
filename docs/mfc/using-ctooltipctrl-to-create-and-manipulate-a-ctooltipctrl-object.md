---
title: CToolTipCtrl Kullanarak bir CToolTipCtrl Nesnesi Oluşturma ve Düzenleme
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], creating
- CToolTipCtrl class [MFC], using
ms.assetid: 0a34583f-f66d-46a1-a239-31b80ea395ad
ms.openlocfilehash: 37dc7bc5a411ebab3737b87fd6977b26cff68178
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79442212"
---
# <a name="using-ctooltipctrl-to-create-and-manipulate-a-ctooltipctrl-object"></a>CToolTipCtrl Kullanarak bir CToolTipCtrl Nesnesi Oluşturma ve Düzenleme

İşte [CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md) kullanımı örneği:

### <a name="to-create-and-manipulate-a-ctooltipctrl"></a>Bir CToolTipCtrl oluşturmak ve değiştirmek için

1. `CToolTipCtrl` nesnesini oluşturun.

1. Windows araç ipucu ortak denetimini oluşturmak ve `CToolTipCtrl` nesnesine eklemek için [Oluştur](../mfc/reference/ctooltipctrl-class.md#create) ' a çağrı yapın.

1. Araç ipucu denetimi ile bir araç kaydetmek için [AddTool](../mfc/reference/ctooltipctrl-class.md#addtool) çağırın. böylece araç ipucunda depolanan bilgiler imleç araç üzerindeyken görüntülenir.

1. Araç ipucunun bir araç için sakladığı bilgileri ayarlamak için [SetToolInfo](../mfc/reference/ctooltipctrl-class.md#settoolinfo) çağırın.

1. Araç için yeni bir sınırlayıcı dikdörtgen ayarlamak üzere [SetToolRect](../mfc/reference/ctooltipctrl-class.md#settoolrect) çağrısı yapın.

1. Verilen aracın sınırlayıcı dikdörtgeni içinde olup olmadığını belirleme noktasını test etmek için [Ittest](../mfc/reference/ctooltipctrl-class.md#hittest) çağırın ve bu durumda araç hakkında bilgi alın.

1. Araç ipucu denetimine kayıtlı araçların sayısını almak için [GetToolCount](../mfc/reference/ctooltipctrl-class.md#gettoolcount) çağrısı yapın.

## <a name="see-also"></a>Ayrıca bkz.

[CToolTipCtrl Kullanma](../mfc/using-ctooltipctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
