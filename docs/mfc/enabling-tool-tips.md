---
title: Araç İpuçlarını Etkinleştirme
ms.date: 11/04/2016
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
ms.openlocfilehash: bdd5c54f9174c42e17db0be7e13ea31acfea2dcf
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84615724"
---
# <a name="enabling-tool-tips"></a>Araç İpuçlarını Etkinleştirme

Pencerenin alt denetimleri için araç ipucu desteğini etkinleştirebilirsiniz (örneğin, form görünümündeki veya iletişim kutusundaki denetimler gibi).

### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>Pencerenin alt denetimleri için araç ipuçlarını etkinleştirmek için

1. `EnableToolTips`Araç ipuçlarını sağlamak istediğiniz pencere için çağrı yapın.

1. [TTN_NEEDTEXT Notification](handling-ttn-needtext-notification-for-tool-tips.md) işleyicinizdeki her denetim için bir dize girin. İşleyici, alt denetimleri (örneğin, form görünümü sınıfınız) içeren pencerenin ileti haritadır. Bu işleyici, denetimi tanımlayan bir işlevi çağırmalıdır ve araç ipucu denetimi tarafından kullanılan metni belirtmek için **pszText** 'i ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[CFrameWnd 'den türetilmemiş pencerelerin araç Ipuçları](tool-tips-in-windows-not-derived-from-cframewnd.md)
