---
title: İlerleme denetimi ayarları | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl class [MFC], settings
- progress controls [MFC], settings
ms.assetid: f4616e91-74fa-4000-ba0d-d3ddc0ee075b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b6b11189e3e0a8381ade372841e6c7b25a5a9fa0
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46434641"
---
# <a name="settings-for-the-progress-control"></a>İlerleme Denetimi Ayarları

İlerleme denetimi için temel ayarlar ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)) aralık ve geçerli konumu. Aralığın işlem süresini temsil eder. Geçerli konumun uygulamanızı işlemi tamamlamaya yönelik yapılan ilerleme durumunu temsil eder. Herhangi bir değişiklik aralık veya konumu çizilmeyi ilerleme durumu denetimini neden.

Varsayılan olarak, aralığın ayarlanmış 0 - 100 ve ilk konumu 0 olarak ayarlanır. İlerleme denetimi için geçerli aralık ayarlarını almak için kullanın [GetRange](../mfc/reference/cprogressctrl-class.md#getrange) üye işlevi. Aralığın değiştirmek için kullanın [SetRange](../mfc/reference/cprogressctrl-class.md#setrange) üye işlevi.

Konumu ayarlamak için kullanın [SetPos](../mfc/reference/cprogressctrl-class.md#setpos). Yeni bir değer belirtmeden geçerli konumunu almak için kullanın [GetPos](../mfc/reference/cprogressctrl-class.md#getpos). Örneğin, yalnızca geçerli işlemin durumunu sorgulamak isteyebilirsiniz.

İlerleme denetimi geçerli konumu adım kullanın [StepIt](../mfc/reference/cprogressctrl-class.md#stepit). Her adım miktarı ayarlamak için kullanın [SetStep](../mfc/reference/cprogressctrl-class.md#setstep)

## <a name="see-also"></a>Ayrıca Bkz.

[CProgressCtrl Kullanma](../mfc/using-cprogressctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

