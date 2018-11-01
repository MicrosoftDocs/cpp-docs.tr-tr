---
title: Üstbilgi Denetimine Öğe Ekleme
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], header
- CHeaderCtrl class [MFC], adding items
- header controls [MFC], adding items to
ms.assetid: 2e9a28b1-7302-4a93-8037-c5a4183e589a
ms.openlocfilehash: c751458a3a2e7e049364ef22a161a3dc9f81df13
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50483570"
---
# <a name="adding-items-to-the-header-control"></a>Üstbilgi Denetimine Öğe Ekleme

Sonra üstbilgi denetimi oluşturma ([CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)) kendi üst penceresinde "gereksinim duyduğunuz kadar çok üstbilgi öğeleri" ekleyin: genellikle bir sütun başına.

### <a name="to-add-a-header-item"></a>Üstbilgi öğesi eklemek için

1. Hazırlama bir [HD_ITEM](/windows/desktop/api/commctrl/ns-commctrl-_hd_itema) yapısı.

1. Çağrı [CHeaderCtrl::InsertItem](../mfc/reference/cheaderctrl-class.md#insertitem), yapısı geçirme.

1. Adım 1 ve 2 ek öğeler için yineleyin.

Daha fazla bilgi için [bir üstbilgi denetimine öğe ekleme](/windows/desktop/Controls/header-controls) Windows SDK.

## <a name="see-also"></a>Ayrıca Bkz.

[CHeaderCtrl Kullanma](../mfc/using-cheaderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

