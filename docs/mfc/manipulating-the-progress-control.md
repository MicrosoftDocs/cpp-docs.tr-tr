---
description: 'Hakkında daha fazla bilgi edinin: Ilerleme denetimini düzenleme'
title: İlerleme Durumu Denetimini Düzenleme
ms.date: 11/04/2016
helpviewer_keywords:
- CProgressCtrl class [MFC], working with
- progress controls [MFC], manipulating
- CProgressCtrl class [MFC], manipulating
- controlling progress controls [MFC]
- CProgressCtrl class [MFC], using
ms.assetid: 9af561d1-980b-4003-a6da-ff79be15bf23
ms.openlocfilehash: cfb89dee0047d910fb983546c71e4a1e4a618f56
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281099"
---
# <a name="manipulating-the-progress-control"></a>İlerleme Durumu Denetimini Düzenleme

İlerleme denetiminin geçerli konumunu değiştirmek için üç yol vardır ([CProgressCtrl](reference/cprogressctrl-class.md)).

- Konum, önceden ayarlanmış bir artış miktarı ile değiştirilebilir.

- Konum, rastgele bir miktar ile değiştirilebilir.

- Konum belirli bir değere değiştirilebilir.

### <a name="to-change-the-position-by-a-preset-amount"></a>Konumu önceden ayarlanmış bir miktara göre değiştirmek için

1. Artış miktarını ayarlamak için [SetStep](reference/cprogressctrl-class.md#setstep) member işlevini kullanın. Varsayılan olarak, bu değer 10 ' dur. Bu değer genellikle denetimin ilk ayarlarından biri olarak ayarlanır. Adım değeri negatif olabilir.

1. Konumu artırmak için [Stepit](reference/cprogressctrl-class.md#stepit) üye işlevini kullanın. Bu, denetimin kendisini yeniden çizmesine neden olur.

    > [!NOTE]
    >  `StepIt` , konumun kaydırılmasına neden olur. Örneğin, bir 1 -100 aralığı, bir adım 20 ve 90 konumu verildiğinde, `StepIt` Konum 10 olarak ayarlanır.

### <a name="to-change-the-position-by-an-arbitrary-amount"></a>Konumu rastgele bir miktara göre değiştirmek için

1. Konumu değiştirmek için [OffsetPos](reference/cprogressctrl-class.md#offsetpos) member işlevini kullanın. `OffsetPos` negatif değerleri kabul eder.

    > [!NOTE]
    >  `OffsetPos`, aksine `StepIt` konumu kaydıramaz. Yeni konum, Aralık içinde kalacak şekilde ayarlanır.

### <a name="to-change-the-position-to-a-specific-value"></a>Konumu belirli bir değere değiştirmek için

1. Konumu belirli bir değere ayarlamak için [SetPos](reference/cprogressctrl-class.md#setpos) üye işlevini kullanın. Gerekirse, yeni konum Aralık dahilinde olacak şekilde ayarlanır.

Genellikle, ilerleme denetimi yalnızca çıkış için kullanılır. Yeni bir değer belirtmeden geçerli konumu almak için [GetPos](reference/cprogressctrl-class.md#getpos)kullanın.

## <a name="see-also"></a>Ayrıca bkz.

[CProgressCtrl Kullanma](using-cprogressctrl.md)<br/>
[Denetimler](controls-mfc.md)
