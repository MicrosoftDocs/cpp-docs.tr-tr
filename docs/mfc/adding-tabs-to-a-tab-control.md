---
title: Sekme Denetimine Sekmeler Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
ms.openlocfilehash: 89132e94396b51bee4a111b963c67d029f3dd9df
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616526"
---
# <a name="adding-tabs-to-a-tab-control"></a>Sekme Denetimine Sekmeler Ekleme

Sekme denetimini oluşturduktan sonra ([CTabCtrl](reference/ctabctrl-class.md)), ihtiyacınız olan kadar sekme ekleyin.

### <a name="to-add-a-tab-item"></a>Sekme öğesi eklemek için

1. Bir [TCITEM](/windows/win32/api/commctrl/ns-commctrl-tcitemw) yapısı hazırlayın.

1. Yapıyı geçirerek [CTabCtrl:: InsertItem](reference/ctabctrl-class.md#insertitem)' ı çağırın.

1. Ek sekme öğeleri için 1 ve 2. adımları tekrarlayın.

Daha fazla bilgi için, bkz. Windows SDK [sekme denetimi oluşturma](/windows/win32/Controls/tab-controls) .

## <a name="see-also"></a>Ayrıca bkz.

[CTabCtrl Kullanma](using-ctabctrl.md)<br/>
[Denetimler](controls-mfc.md)
