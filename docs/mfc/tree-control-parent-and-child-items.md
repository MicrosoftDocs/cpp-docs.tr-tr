---
title: "Ağaç denetimi üst ve alt öğeleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- parent items in CTreeCtrl [MFC]
- child items in tree control [MFC]
- CTreeCtrl class [MFC], parent and child items
- tree controls [MFC], parent and child items
ms.assetid: abcea1e4-fe9b-40d9-86dc-1db235f8f103
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: feaf59932da66be2bf269316c7ee9587d4037b3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="tree-control-parent-and-child-items"></a>Ağaç Denetimi Üst ve Alt Öğeleri
Ağaç denetimi herhangi bir öğeye ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) kendisiyle ilişkili alt öğeleri adlı alt öğeler listesini sağlayabilirsiniz. Bir veya daha fazla alt öğelerine sahip bir öğe üst öğe adı verilir. Bir alt öğesi kendi üst öğesi altında görüntülenir ve üst bağımlı olan belirtmek için girintili. Üst öğeye sahip bir öğe hiyerarşisinin en üstünde olduğu ve bir kök öğe adı verilir.  
  
 Belirli bir zamanda, bir üst öğenin alt öğeleri listesi durumunu genişletilmiş daraltılmış ya da. Durum genişletildiğinde, alt öğeler üst öğenin altında görüntülenir. Daraltıldığında, alt öğeler görüntülenmez. Liste otomatik olarak kullanıcı üst öğeyi tıklattığında veya üst varsa genişletilmiş ve daraltılmış durumlar arasında değiştirir **TVS_HASBUTTONS** kullanıcı üst öğeyle ilişkili düğmesini tıklattığında stili. Bir uygulama genişletebilir veya alt öğeleri kullanarak daraltabilirsiniz [genişletme](../mfc/reference/ctreectrl-class.md#expand) üye işlevi.  
  
 Çağırarak ağaç denetime öğe ekleme [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) üye işlevi. Bu işlev bir işleyicisini döndürür **HTREEITEM** öğeyi benzersiz olarak tanıtan türü. Bir öğe eklerken, yeni öğenin üst öğesinin tanıtıcısı belirtmeniz gerekir. Belirtirseniz **NULL** veya **TVI_ROOT** değeri bir üst öğesi tanıtıcı yerine [TVINSERTSTRUCT](http://msdn.microsoft.com/library/windows/desktop/bb773452) yapısı veya `hParent` parametresi, bir kök olarak eklenen öğe öğe.  
  
 Ağaç denetimi gönderir bir [TVN_ITEMEXPANDING](http://msdn.microsoft.com/library/windows/desktop/bb773537) bir üst öğenin alt öğeleri listesi hakkında genişletilebilir veya daraltılabilir üzere olduğunda uyarı iletisi. Bildirim değişikliği engellemek veya alt öğe listesinin durumuna bağlıdır üst öğesi özniteliklerini ayarlamak için fırsatı verir. Ağaç denetimi gönderir listenin durumunu değiştirdikten sonra bir [TVN_ITEMEXPANDED](http://msdn.microsoft.com/library/windows/desktop/bb773533) bildirim iletisi.  
  
 Bir alt öğe listesi genişletildiğinde göre üst öğesi girintili olur. Kullanarak girinti miktarını ayarlayabilirsiniz [SetIndent](../mfc/reference/ctreectrl-class.md#setindent) üye işlevini veya alma kullanarak geçerli tutar [GetIndent](../mfc/reference/ctreectrl-class.md#getindent) üye işlevi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

