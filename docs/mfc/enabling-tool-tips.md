---
title: Araç ipuçlarını etkinleştirme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- initializing tool tips [MFC]
- enabling tool tips [MFC]
- tool tips [MFC], initializing
- tool tips [MFC], enabling
ms.assetid: 06b7c889-7722-4ce6-8b88-9efa50fe6369
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 968d31b49c6d2b2fe5a5f69e04f58f17de8df5a2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46440491"
---
# <a name="enabling-tool-tips"></a>Araç İpuçlarını Etkinleştirme

(Örneğin, bir form görünümü veya iletişim kutusu denetimleri) pencerenin alt denetimler için araç ipucu desteği etkinleştirebilirsiniz.

### <a name="to-enable-tool-tips-for-the-child-controls-of-a-window"></a>Pencerenin alt denetimler için araç ipuçları etkinleştirmek için

1. Çağrı `EnableToolTips` araç ipuçları sağlamak istediğiniz penceresi.

1. Her denetim için bir dize sağlayın, [TTN_NEEDTEXT bildirimini](../mfc/handling-ttn-needtext-notification-for-tool-tips.md) işleyici. Alt denetimler (örneğin, form görünümü sınıfı) içeren bir pencere ileti eşlemede işleyicidir. Bu işleyici, bir işlev çağırmalıdır denetimi tanımlar ve ayarlar **pszText** araç ipucu denetimi tarafından kullanılan gösterilen yazıyı belirtmek için.

## <a name="see-also"></a>Ayrıca Bkz.

[CFrameWnd'den Türetilmemiş Pencerelerde Araç İpuçları](../mfc/tool-tips-in-windows-not-derived-from-cframewnd.md)

