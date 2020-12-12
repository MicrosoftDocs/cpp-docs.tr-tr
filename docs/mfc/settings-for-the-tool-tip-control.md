---
description: 'Hakkında daha fazla bilgi edinin: araç Ipucu denetimi için ayarlar'
title: Araç İpucu Denetimi için Ayarlar
ms.date: 11/04/2016
helpviewer_keywords:
- tool tips [MFC], activating
- CToolTipCtrl class [MFC], settings
ms.assetid: ff8c5c46-2047-403a-bd98-ffec3d21ee3a
ms.openlocfilehash: 789f33a7e8e960f52589588bcda49a12889fa0d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217035"
---
# <a name="settings-for-the-tool-tip-control"></a>Araç İpucu Denetimi için Ayarlar

Araç ipucu denetimini ([CToolTipCtrl](../mfc/reference/ctooltipctrl-class.md)) etkin ya da etkin değil olarak ayarlayabilirsiniz. Etkin olacak şekilde ayarladığınızda, imleç bir araç üzerindeyken araç ipucu denetimi görünür. Devre dışı olarak ayarladığınızda, imleç bir araç üzerinde olsa bile araç ipucu denetimi görünmez. Araç ipucu denetimini etkinleştirmek veya devre dışı bırakmak için [Etkinleştir](../mfc/reference/ctooltipctrl-class.md#activate) ' i çağırın.

İmleç bir araç üzerindeyken, TTS_ALWAYSTIP stilini kullanarak araç ipucu denetiminin sahip penceresinin etkin veya devre dışı olup olmadığına bakılmaksızın araç ipucunu göstermek için etkin bir araç ipucu ayarlayabilirsiniz. Bu stili kullanmıyorsanız araç ipucu denetimi, aracın sahip penceresi etkin olduğunda görüntülenir, ancak etkin olmadığında görüntülenmez.

Çoğu uygulama, menü komutlarına karşılık gelen araçları içeren araç çubuklarını içerir. Bu tür araçlar için, araç ipucu denetiminin ilgili menü öğesiyle aynı metni görüntülemesi kullanışlıdır. Sistem, denetimin TTS_NOPREFIX stiline sahip olmadığı durumlar dışında, bir araç ipucu denetimine geçirilen tüm dizelerdeki ve işareti (&) Hızlandırıcı karakterlerini otomatik olarak kaldırır.

## <a name="see-also"></a>Ayrıca bkz.

[CToolTipCtrl Kullanma](../mfc/using-ctooltipctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
