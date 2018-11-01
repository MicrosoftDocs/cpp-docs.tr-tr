---
title: Ağaç Denetimi Üst ve Alt Öğeleri
ms.date: 11/04/2016
helpviewer_keywords:
- parent items in CTreeCtrl [MFC]
- child items in tree control [MFC]
- CTreeCtrl class [MFC], parent and child items
- tree controls [MFC], parent and child items
ms.assetid: abcea1e4-fe9b-40d9-86dc-1db235f8f103
ms.openlocfilehash: ca74f85228a7b428d277395dfdd1d7172f8247f1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544982"
---
# <a name="tree-control-parent-and-child-items"></a>Ağaç Denetimi Üst ve Alt Öğeleri

Ağaç denetimi herhangi bir öğeye ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) alt öğeleri, kendisiyle ilişkili adlı alt öğeleri listesini sağlayabilirsiniz. Bir veya daha fazla alt öğelerine sahip bir öğe, bir üst öğesi olarak adlandırılır. Bir alt öğesi kendi üst öğesi görüntülenir ve üst bağımlı olduğunu belirten girintili hale getirilir. Üst öğeye sahip bir öğe hiyerarşisinin en üstünde olduğu ve bir kök öğe adı verilir.

Herhangi bir zamanda bir üst öğenin alt öğelerinin listesini durumunu ya da Genişletilebilir veya daraltılabilir. Durumu genişletildiğinde, üst öğenin alt öğeler görüntülenir. Daraltıldığında, alt öğelerini görüntülenmez. Liste otomatik olarak üst öğe kullanıcı çift tıkladığında veya üstü yoksa genişletilmiş ve daraltılmış durumları arasında değiştirir **TVS_HASBUTTONS** kullanıcı üst öğeyle ilişkili düğmeyi tıkladığında stili. Bir uygulama genişletebilir veya kullanarak alt öğelerini Daralt [genişletme](../mfc/reference/ctreectrl-class.md#expand) üye işlevi.

Çağırarak bir ağaç denetimine bir öğe ekleme [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) üye işlevi. Bu işlev, bir tanıtıcı döndürür **HTREEITEM** öğeyi benzersiz olarak tanımlayan tür. Bir öğe eklendiğinde, yeni öğenin üst öğesinin tanıtıcısı belirtmeniz gerekir. Belirtirseniz **NULL** veya **TVI_ROOT** değeri yerine bir üst öğesi tutucu [TVINSERTSTRUCT](/windows/desktop/api/commctrl/ns-commctrl-tagtvinsertstructa) yapısı veya *hParent* parametre öğesi kök öğesi olarak eklenir.

Ağaç denetimi gönderen bir [TVN_ITEMEXPANDING](/windows/desktop/Controls/tvn-itemexpanding) yaklaşık genişletilmiş veya daraltılmış bir üst öğenin alt öğelerinin listesi olduğunda bildirim iletisi. Bildirim, değişikliği engellemek veya alt öğelerin listesini durumuna bağlı herhangi bir özniteliği üst öğenin ayarlamak için bir fırsat sunar. Ağaç denetimi gönderir listenin durumunu değiştirdikten sonra bir [TVN_ITEMEXPANDED](/windows/desktop/Controls/tvn-itemexpanded) bildirim iletisi.

Alt öğe listesi genişletildiğinde göre üst öğesi girintili hale getirilir. Girinti miktarını kullanarak ayarlayabilirsiniz [SetIndent](../mfc/reference/ctreectrl-class.md#setindent) üye işlevini veya Al kullanarak geçerli tutarın [GetIndent](../mfc/reference/ctreectrl-class.md#getindent) üye işlevi.

## <a name="see-also"></a>Ayrıca Bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

