---
title: Sekme Denetimine Sekmeler Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
ms.openlocfilehash: 8915b3af083ebe318e8527b2f83099bf61e7e3ce
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69509301"
---
# <a name="adding-tabs-to-a-tab-control"></a>Sekme Denetimine Sekmeler Ekleme

Sekme denetimini oluşturduktan sonra ([CTabCtrl](../mfc/reference/ctabctrl-class.md)), ihtiyacınız olan kadar sekme ekleyin.

### <a name="to-add-a-tab-item"></a>Sekme öğesi eklemek için

1. Bir [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) yapısı hazırlayın.

1. Yapıyı geçirerek [CTabCtrl:: InsertItem](../mfc/reference/ctabctrl-class.md#insertitem)' ı çağırın.

1. Ek sekme öğeleri için 1 ve 2. adımları tekrarlayın.

Daha fazla bilgi için, bkz. Windows SDK [sekme denetimi oluşturma](/windows/win32/Controls/tab-controls) .

## <a name="see-also"></a>Ayrıca bkz.

[CTabCtrl Kullanma](../mfc/using-ctabctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
