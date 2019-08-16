---
title: Ağaç Denetimi Üst ve Alt Öğeleri
ms.date: 11/04/2016
helpviewer_keywords:
- parent items in CTreeCtrl [MFC]
- child items in tree control [MFC]
- CTreeCtrl class [MFC], parent and child items
- tree controls [MFC], parent and child items
ms.assetid: abcea1e4-fe9b-40d9-86dc-1db235f8f103
ms.openlocfilehash: 5a02194ccef8eca81971bb4e8ae24d859e578bcc
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69513963"
---
# <a name="tree-control-parent-and-child-items"></a>Ağaç Denetimi Üst ve Alt Öğeleri

Ağaç denetimindeki herhangi bir öğe ([Ctreecu](../mfc/reference/ctreectrl-class.md)), onunla ilişkili alt öğeler olarak adlandırılan alt öğeleri içeren bir listeye sahip olabilir. Bir veya daha fazla alt öğeye sahip bir öğeye üst öğe denir. Alt öğe, üst öğesinin altında görüntülenir ve üst öğenin alt öğesi olduğunu göstermek için girintilenir. Üst öğesi olmayan bir öğe hiyerarşinin en üstünde yer alan ve kök öğe olarak adlandırılır.

Herhangi bir zamanda, bir üst öğenin alt öğe listesi durumunun genişletilmiş veya daraltılmış olması olabilir. Durum genişletildiğinde, alt öğeler üst öğenin altında görüntülenir. Daraltıldığında alt öğeler görüntülenmez. Kullanıcı üst öğeyi çift tıklattığında veya üst öğe **tvs_hasbuttons** stiline sahipse, Kullanıcı üst öğeyle ilişkili düğmeye tıkladığında liste otomatik olarak genişletilmiş ve daraltılmış durumlar arasında geçiş yapar. Bir uygulama [Genişlet](../mfc/reference/ctreectrl-class.md#expand) üye işlevini kullanarak alt öğeleri genişletebilir veya daraltabilir.

[InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) üye işlevini çağırarak ağaç denetimine bir öğe eklersiniz. Bu işlev, öğeyi benzersiz bir şekilde tanımlayan **Htreeitem** türünün bir tanıtıcısını döndürür. Bir öğe eklenirken, yeni öğenin üst öğesinin tanıtıcısını belirtmeniz gerekir. [TVINSERTSTRUCT](/windows/win32/api/commctrl/ns-commctrl-tvinsertstructw) yapısı veya *hParent* parametresinde bir üst öğe tanıtıcısı yerine **null** veya **TVI_ROOT** değerini belirtirseniz, öğe bir kök öğe olarak eklenir.

Ağaç denetimi bir üst öğenin alt öğe listesi genişletilmekte veya daraltılacak şekilde olduğunda bir [TVN_ITEMEXPANDING](/windows/win32/Controls/tvn-itemexpanding) bildirim iletisi gönderir. Bildirim, değişikliği önleme veya alt öğe listesinin durumuna bağlı üst öğenin herhangi bir özniteliğini ayarlamayı sağlayan bir fırsat sağlar. Listenin durumunu değiştirdikten sonra, ağaç denetimi bir [TVN_ITEMEXPANDED](/windows/win32/Controls/tvn-itemexpanded) bildirim iletisi gönderir.

Alt öğelerin bir listesi genişletildiğinde, üst öğeye göre girintilenir. {1 & gt; Getgirintile & lt; 1} öğesini kullanarak [Setgirintile](../mfc/reference/ctreectrl-class.md#setindent) üye işlevini kullanarak veya geçerli miktarı [](../mfc/reference/ctreectrl-class.md#getindent) elde edebilirsiniz.

## <a name="see-also"></a>Ayrıca bkz.

[CTreeCtrl Kullanma](../mfc/using-ctreectrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
