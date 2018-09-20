---
title: Yansımış iletileri işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 99fc9c30ea85ba3f94fa811464f023da0eeea37e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438684"
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
