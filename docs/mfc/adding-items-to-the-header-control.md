---
title: Üstbilgi Denetimine Öğe Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
ms.openlocfilehash: 5749a0cae2dfe7e6c9f4c166eca487e36c2d21d2
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616463"
---
# <a name="adding-items-to-the-header-control"></a>Üstbilgi Denetimine Öğe Ekleme

Üst penceresinde üstbilgi denetiminizi ([CHeaderCtrl](reference/cheaderctrl-class.md)) oluşturduktan sonra, gerek duyduğunuz kadar "Başlık öğesi" ekleyin: genellikle her sütun için bir.

### <a name="to-add-a-header-item"></a>Üst bilgi öğesi eklemek için

1. [HD_ITEM](/windows/win32/api/commctrl/ns-commctrl-hditemw) yapısını hazırlayın.

1. Yapıyı geçirerek [CHeaderCtrl:: InsertItem](reference/cheaderctrl-class.md#insertitem)' ı çağırın.

1. Ek öğeler için 1 ve 2. adımları tekrarlayın.

Daha fazla bilgi için bkz. Windows SDK [üst bilgi denetimine öğe ekleme](/windows/win32/Controls/header-controls) .

## <a name="see-also"></a>Ayrıca bkz.

[CHeaderCtrl Kullanma](using-cheaderctrl.md)<br/>
[Denetimler](controls-mfc.md)
