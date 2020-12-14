---
description: 'Daha fazla bilgi edinin: yansıtılan Iletileri Işleme'
title: Yansımış İletileri İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- message handling [MFC], reflected messages
- reflected messages, handling
ms.assetid: 147a4e0c-51cc-4447-a8e1-c28b4cece578
ms.openlocfilehash: 4093c2feaa263470bc07df6feec32b12fea01542
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97254917"
---
# <a name="handling-reflected-messages"></a>Yansımış İletileri İşleme

İleti yansıtma, denetimin içinde **WM_CTLCOLOR**, **WM_COMMAND** ve **WM_NOTIFY** gibi bir denetim için iletileri işlemenize olanak sağlar. Bu, denetimi daha kendinden ve taşınabilir hale getirir. Mekanizma, Windows ortak denetimleriyle birlikte ve ActiveX denetimleriyle birlikte (eski adıyla OLE denetimleri olarak adlandırılır) kullanılabilir.

İleti yansıtma, `CWnd` türetilmiş sınıflarınızı daha kolay bir şekilde yeniden kullanmanıza olanak tanır. İleti yansıtma, özel **ON_XXX_REFLECT** ileti eşleme girdileri kullanılarak [CWnd:: OnChildNotify](reference/cwnd-class.md#onchildnotify)aracılığıyla çalışarak: örneğin, **ON_CTLCOLOR_REFLECT** ve **ON_CONTROL_REFLECT**. [Teknik notta 62](tn062-message-reflection-for-windows-controls.md) ileti yansıması daha ayrıntılı olarak açıklanmaktadır.

## <a name="what-do-you-want-to-do"></a>Ne yapmak istiyorsunuz?

- [İleti yansıtma hakkında daha fazla bilgi](tn062-message-reflection-for-windows-controls.md)

- [Ortak denetim için ileti yansıması uygulama](tn062-message-reflection-for-windows-controls.md)

- [ActiveX denetimi için ileti yansıması uygulama](mfc-activex-controls-subclassing-a-windows-control.md)

## <a name="see-also"></a>Ayrıca bkz.

[Ileti Işleyici Işlevlerini bildirme](declaring-message-handler-functions.md)
