---
title: İlerleme Denetimi Ayarları
ms.date: 11/04/2016
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
ms.openlocfilehash: 444dc45c816e0dfc2fd45bad999ad90c2acacc01
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50481789"
---
# <a name="settings-for-the-progress-control"></a>İlerleme Denetimi Ayarları

İlerleme denetimi için temel ayarlar ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)) aralık ve geçerli konumu. Aralığın işlem süresini temsil eder. Geçerli konumun uygulamanızı işlemi tamamlamaya yönelik yapılan ilerleme durumunu temsil eder. Herhangi bir değişiklik aralık veya konumu çizilmeyi ilerleme durumu denetimini neden.

Varsayılan olarak, aralığın ayarlanmış 0 - 100 ve ilk konumu 0 olarak ayarlanır. İlerleme denetimi için geçerli aralık ayarlarını almak için kullanın [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) üye işlevi. Aralığın değiştirmek için kullanın [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) üye işlevi.

Konumu ayarlamak için kullanın [SetPos](../mfc/reference/cprogressctrl-class.md#setpos). Yeni bir değer belirtmeden geçerli konumunu almak için kullanın [GetPos](../mfc/reference/cprogressctrl-class.md#getpos). Örneğin, yalnızca geçerli işlemin durumunu sorgulamak isteyebilirsiniz.

İlerleme denetimi geçerli konumu adım kullanın [StepIt](../mfc/reference/cprogressctrl-class.md#stepit). Her adım miktarı ayarlamak için kullanın [SetStep](../mfc/reference/cprogressctrl-class.md#setstep)

## <a name="see-also"></a>Ayrıca Bkz.

[CProgressCtrl Kullanma](../mfc/using-cprogressctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

