---
title: Sekme Denetimine Sekmeler Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
ms.openlocfilehash: be622035355a68d1527a515bfdcb633a3af274d8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50618276"
---
# <a name="adding-tabs-to-a-tab-control"></a>Sekme Denetimine Sekmeler Ekleme

Sekme denetimi oluşturduktan sonra ([CTabCtrl](../mfc/reference/ctabctrl-class.md)), ihtiyacınız kadar sekme ekleyin.

### <a name="to-add-a-tab-item"></a>Sekme öğesi eklemek için

1. Hazırlama bir [TCITEM](/windows/desktop/api/commctrl/ns-commctrl-tagtcitema) yapısı.

1. Çağrı [CTabCtrl::InsertItem](../mfc/reference/ctabctrl-class.md#insertitem), yapısı geçirme.

1. Adım 1 ve 2 ek sekme öğeleri için yineleyin.

Daha fazla bilgi için [sekme denetimi oluşturma](/windows/desktop/Controls/tab-controls) Windows SDK.

## <a name="see-also"></a>Ayrıca Bkz.

[CTabCtrl Kullanma](../mfc/using-ctabctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

