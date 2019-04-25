---
title: Ağaç Denetimi Bildirim İletileri
ms.date: 11/04/2016
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
ms.openlocfilehash: 90e2e112d7862dfed7d8af31cfb72ff45633a2c1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62181650"
---
# <a name="tree-control-notification-messages"></a>Ağaç Denetimi Bildirim İletileri

Ağaç denetimi ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) wm_notıfy iletileri aşağıdaki bildirim iletilerini gönderir:

|Bildirim iletisi|Açıklama|
|--------------------------|-----------------|
|TVN_BEGINDRAG|Bir Sürükle ve bırak işleminin başlangıç sinyalleri|
|TVN_BEGINLABELEDIT|Yerinde etiket düzenleme başlangıç sinyalleri|
|TVN_BEGINRDRAG|Sağ fare düğmesini kullanarak, bir Sürükle ve bırak işleminin başlangıç sinyalleri|
|TVN_DELETEITEM|Belirli bir öğeyi silme işlemi sinyalleri|
|TVN_ENDLABELEDIT|Etiket düzenleme sonuna sinyalleri|
|TVN_GETDISPINFO|Bir öğeyi görüntülemek için ağaç denetimi gerektirdiğini bilgisini ister|
|TVN_ITEMEXPANDED|Bir üst öğenin alt öğelerinin listesini genişletilmiş veya daraltılmış, sinyaller|
|TVN_ITEMEXPANDING|Yaklaşık genişletilmiş veya daraltılmış bir üst öğenin alt öğelerinin listesi olan sinyalleri|
|TVN_KEYDOWN|Klavye olay sinyalini verir|
|TVN_SELCHANGED|Seçimin bir öğeden diğerine değiştiğini sinyalleri|
|TVN_SELCHANGING|Seçimin bir öğeden diğerine değiştirilmek üzere olan sinyalleri|
|TVN_SETDISPINFO|Bir öğe için tutulan bilgileri güncelleştirmek için bildirim|

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
