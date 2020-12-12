---
description: 'Daha fazla bilgi edinin: araç Ipuçlarını etkinleştirme'
title: Araç İpuçlarını Etkinleştirme
ms.date: 11/04/2016
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
ms.openlocfilehash: 677d2cc071e87f62f9bd2e700d8fdba166dfdee7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97290953"
---
# <a name="enabling-tool-tips"></a>Araç İpuçlarını Etkinleştirme

Pencerenin alt denetimleri için araç ipucu desteğini etkinleştirebilirsiniz (örneğin, form görünümündeki veya iletişim kutusundaki denetimler gibi).

### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>Pencerenin alt denetimleri için araç ipuçlarını etkinleştirmek için

1. `EnableToolTips`Araç ipuçlarını sağlamak istediğiniz pencere için çağrı yapın.

1. [TTN_NEEDTEXT Notification](handling-ttn-needtext-notification-for-tool-tips.md) işleyicinizdeki her denetim için bir dize girin. İşleyici, alt denetimleri (örneğin, form görünümü sınıfınız) içeren pencerenin ileti haritadır. Bu işleyici, denetimi tanımlayan bir işlevi çağırmalıdır ve araç ipucu denetimi tarafından kullanılan metni belirtmek için **pszText** 'i ayarlar.

## <a name="see-also"></a>Ayrıca bkz.

[CFrameWnd 'den türetilmemiş pencerelerin araç Ipuçları](tool-tips-in-windows-not-derived-from-cframewnd.md)
