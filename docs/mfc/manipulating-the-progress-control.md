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
ms.openlocfilehash: 415061306c5e743b9ed95ee5c7105133d2e4d340
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347409"
---
# <a name="manipulating-the-progress-control"></a>İlerleme Durumu Denetimini Düzenleme
Bir ilerleme denetiminin geçerli konumunu değiştirmek için üç yolu vardır ([CProgressCtrl](../mfc/reference/cprogressctrl-class.md)).  
  
-   Konumu önceden belirlenmiş artışı tutarına göre değiştirilebilir.  
  
-   Konumu rasgele bir miktarda değiştirilebilir.  
  
-   Belirli bir değere konumu değiştirilebilir.  
  
### <a name="to-change-the-position-by-a-preset-amount"></a>Önceden belirlenmiş bir miktarda konumu değiştirmek için  
  
1.  Kullanım [SetStep](../mfc/reference/cprogressctrl-class.md#setstep) artış tutarı ayarlamak için üye işlevi. Varsayılan olarak, bu değer 10'dur. Bu değer genellikle denetimi için ilk ayarlar biri olarak ayarlanır. Adım değeri negatif olabilir.  
  
2.  Kullanım [StepIt](../mfc/reference/cprogressctrl-class.md#stepit) konumu artırmak için üye işlevi. Bu denetimin kendisini yeniden boyutlandırmaya neden olur.  
  
    > [!NOTE]
    >  `StepIt` kaydırma konumunu neden olur. Örneğin, bir aralığı 1 -100, 20 adımında ve 90, konumunu verilen `StepIt` konumu 10'a ayarlanır.  
  
### <a name="to-change-the-position-by-an-arbitrary-amount"></a>Rastgele bir miktarda konumu değiştirmek için  
  
1.  Kullanım [OffsetPos](../mfc/reference/cprogressctrl-class.md#offsetpos) konumu değiştirmek için üye işlevi. `OffsetPos` negatif değerler kabul eder.  
  
    > [!NOTE]
    >  `OffsetPos`, farklı `StepIt`, konumu kaydırılır değil. Yeni bir konuma aralıkta kalması için ayarlanır.  
  
### <a name="to-change-the-position-to-a-specific-value"></a>Belirli bir değere konumu değiştirmek için  
  
1.  Kullanım [SetPos](../mfc/reference/cprogressctrl-class.md#setpos) konumu belirli bir değere ayarlamak için üye işlevi. Gerekirse, yeni konumu aralık içinde olacak şekilde ayarlanır.  
  
 Genellikle, ilerleme durumu denetimini yalnızca çıktı için kullanılır. Yeni bir değer belirtmeden geçerli konumunu almak için [GetPos](../mfc/reference/cprogressctrl-class.md#getpos).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CProgressCtrl kullanma](../mfc/using-cprogressctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

