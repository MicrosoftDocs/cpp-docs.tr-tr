---
title: İlerleme Durumu Denetimini Düzenleme
ms.date: 11/04/2016
helpviewer_keywords:
- CProgressCtrl class [MFC], working with
- progress controls [MFC], manipulating
- CProgressCtrl class [MFC], manipulating
- controlling progress controls [MFC]
- CProgressCtrl class [MFC], using
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
ms.openlocfilehash: c9da6f8048adf1c7da184570ff7f94deee7441e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62279196"
---
# <a name="manipulating-the-progress-control"></a>İlerleme Durumu Denetimini Düzenleme

İlerleme denetimi konumunu değiştirmek için üç yol vardır ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)).

- Konumu, bir önayarlı artışı miktarda değiştirilebilir.

- Konumu rastgele bir miktarda değiştirilebilir.

- Belirli bir değere konumu değiştirilebilir.

### <a name="to-change-the-position-by-a-preset-amount"></a>Önceden oluşturulmuş bir miktarda konumunu değiştirmek için

1. Kullanım [SetStep](../mfc/reference/cprogressctrl-class.md#setstep) artışı ayarlama üye işlevi. Varsayılan olarak, bu değer 10'dur. Bu değer genellikle Denetim ve ilk ayarları biri olarak ayarlayın. Adım değeri negatif olabilir.

1. Kullanım [StepIt](../mfc/reference/cprogressctrl-class.md#stepit) konumu artırmak için üye işlevi. Bu, denetimin çizilmeyi neden olur.

    > [!NOTE]
    >  `StepIt` kaydırmak için konumun neden olur. Örneğin, bir aralık 1 -100, 20 bir adım ve 90, konumunu, verilen `StepIt` konumu 10'a ayarlanır.

### <a name="to-change-the-position-by-an-arbitrary-amount"></a>Rastgele bir miktarda konumunu değiştirmek için

1. Kullanım [OffsetPos](../mfc/reference/cprogressctrl-class.md#offsetpos) konumunu değiştirmek için üye işlevi. `OffsetPos` negatif değerler kabul eder.

    > [!NOTE]
    >  `OffsetPos`, farklı `StepIt`, konumu desteklemez. Yeni konumunu aralıkta kalması için ayarlanır.

### <a name="to-change-the-position-to-a-specific-value"></a>Belirli bir değere konumunu değiştirmek için

1. Kullanım [SetPos](../mfc/reference/cprogressctrl-class.md#setpos) konumu belirli bir değere ayarlamak için üye işlevi. Gerekirse, yeni konumunu aralığında olacak şekilde ayarlanır.

Genellikle, ilerleme durumu denetimini yalnızca çıktı için kullanılır. Yeni bir değer belirtmeden geçerli konumunu almak için kullanın [GetPos](../mfc/reference/cprogressctrl-class.md#getpos).

## <a name="see-also"></a>Ayrıca bkz.

[CProgressCtrl Kullanma](../mfc/using-cprogressctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
