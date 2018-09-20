---
title: İlerleme durumu denetimini düzenleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CProgressCtrl class [MFC], working with
- progress controls [MFC], manipulating
- CProgressCtrl class [MFC], manipulating
- controlling progress controls [MFC]
- CProgressCtrl class [MFC], using
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9fe784dfd63ec5c27a3695df3e6bc42ae0de2f7f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46416779"
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

## <a name="see-also"></a>Ayrıca Bkz.

[CProgressCtrl Kullanma](../mfc/using-cprogressctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

