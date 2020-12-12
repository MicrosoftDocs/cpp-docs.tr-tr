---
description: 'Hakkında daha fazla bilgi edinin: Sekme denetimine sekmeler ekleme'
title: Sekme Denetimine Sekmeler Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- tab controls [MFC], adding tabs
- putting tabs on CTabCtrls [MFC]
- CTabCtrl class [MFC], adding tabs
- tabs [MFC], adding to CTabCtrl class [MFC]
ms.assetid: 7f3d9340-e3c7-4c71-9912-be57534ecc78
ms.openlocfilehash: ca25edf349fb11271d4e355241f4724d11bc4ac0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185472"
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
