---
title: Araç İpucu Denetimi için Ayarlar
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
ms.openlocfilehash: 5cc72401da95e63520b544865ea509a8ad219bda
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57271937"
---
# <a name="settings-for-the-tool-tip-control"></a>Araç İpucu Denetimi için Ayarlar

Araç ipucunu denetimini ayarlayabilirsiniz ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) etkin veya devre dışı edilecek. İmleç bir aracı üzerinde olduğunda, etkin olarak ayarladığınızda, araç ipucunu denetimini görünür. Etkin olarak ayarladığınızda, imleç bir araç olsa bile, araç ipucunu denetimini görünmüyor. Çağrı [etkinleştirme](../mfc/reference/ctooltipctrl-class.md#activate) etkinleştirme veya devre dışı bir araç ipucu denetimi.

İmleç bir aracı üzerinde olduğunda, sahip penceresine araç ipucu denetiminin TTS_ALWAYSTIP stili kullanarak etkin veya devre dışı olup olmadığını araç ipucu görüntülemek için bir etkin araç ipucu ayarlayabilirsiniz. Bu stil kullanmazsanız, araç ipucunu denetimini Aracı'nın sahibi pencere etkin olduğunda, ancak etkin olmadığı durumlarda görüntülenir.

Çoğu uygulama, menü komutlarını karşılık gelen araçlarla araç çubuklarını içerir. Gibi araçlar için karşılık gelen bir menü öğesi olarak aynı metni görüntülemek araç ipucu denetimi için uygundur. Denetim TTS_NOPREFIX stilde sürece sistem işareti (&) tüm dizeleri Hızlandırıcı karakterler bir araç ipucu denetimi için geçirilen otomatik olarak kaldırır.

## <a name="see-also"></a>Ayrıca bkz.

[CToolTipCtrl Kullanma](../mfc/using-ctooltipctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
