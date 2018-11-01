---
title: Yansımış İletileri İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
ms.openlocfilehash: 9b580c0c8b8fc970d69f5c57f69bbbbe65e22497
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449874"
---
# <a name="handling-reflected-messages"></a>Yansımış İletileri İşleme

Yansıma gibi bir denetimin iletileri işlemenize olanak tanır ileti **WM_CTLCOLOR**, **WM_COMMAND**, ve **wm_notıfy**, denetimin kendi içinde. Bu, daha müstakil ve taşınabilir denetim sağlar. Windows ortak denetimleri (eski adı OLE denetimleri de denir) ActiveX denetimleriyle yanı sıra mekanizması çalışır.

İleti yansıma, yeniden kullanmanıza olanak tanır, `CWnd`-türetilmiş sınıfları daha kolay. İleti yansıma works aracılığıyla [CWnd::OnChildNotify](../mfc/reference/cwnd-class.md#onchildnotify), özel kullanarak **ON_XXX_REFLECT** ileti eşlemesi girişleri: Örneğin, **ON_CTLCOLOR_REFLECT** ve **ON_CONTROL_REFLECT**. [Teknik Not 62](../mfc/tn062-message-reflection-for-windows-controls.md) ileti yansıması daha ayrıntılı açıklanmaktadır.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz

- [İleti yansıması hakkında daha fazla bilgi edinin](../mfc/tn062-message-reflection-for-windows-controls.md)

- [Bir ortak denetimi için ileti yansıması uygulayın](../mfc/tn062-message-reflection-for-windows-controls.md)

- [ActiveX denetimi için ileti yansıması uygulayın](../mfc/mfc-activex-controls-subclassing-a-windows-control.md)

## <a name="see-also"></a>Ayrıca Bkz.

[İleti İşleyici İşlevlerini Bildirme](../mfc/declaring-message-handler-functions.md)
