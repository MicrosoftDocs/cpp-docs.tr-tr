---
title: "Ağaç denetimlerini kullanma | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CTreeCtrl class [MFC], using
- tree controls [MFC], about tree controls
ms.assetid: 4e92941a-e477-4fb1-b1ce-4abeafbef1c1
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ea3b7e0348cb21aa4338293f7cc1119e380f92dc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="using-tree-controls"></a>Ağaç Denetimlerini Kullanma
Ağaç denetimi tipik kullanımını ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) deseni izler:  
  
-   Denetim oluşturulur. Denetim bir iletişim kutusu şablonunda belirtilirse veya kullanıyorsanız, `CTreeView`, oluşturma, iletişim kutusu veya Görünüm oluşturulduğunda otomatiktir. Ağaç denetimi alt pencere başka bir pencere olarak oluşturmak istiyorsanız, kullanmak [oluşturma](../mfc/reference/ctreectrl-class.md#create) üye işlevi.  
  
-   Ağaç denetim görüntüleri kullanmak istiyorsanız, bir resim listesi aranarak [SetImageList](../mfc/reference/ctreectrl-class.md#setimagelist). Çağırarak girinti değiştirebilirsiniz [SetIndent](../mfc/reference/ctreectrl-class.md#setindent). Bunu yapmak için iyi bir zamandır bulunduğu [OnInitDialog](../mfc/reference/cdialog-class.md#oninitdialog) (için iletişim kutularındaki denetimler) veya [OnInitialUpdate](../mfc/reference/cview-class.md#oninitialupdate) (için görünümler).  
  
-   Verileri çağırarak denetime yerleştirme `CTreeCtrl`'s [InsertItem](../mfc/reference/ctreectrl-class.md#insertitem) işlevi için her bir veri öğesi için bir kez. `InsertItem`tanıtıcı döndürür, daha sonra zaman gibi başvurduğu için kullanabileceğiniz öğesine alt öğeleri ekleniyor. Verileri başlatma için iyi bir zamandır bulunduğu `OnInitDialog` (için iletişim kutularındaki denetimler) veya `OnInitialUpdate` (için görünümler).  
  
-   Kullanıcı denetimi ile etkileşim gibi çeşitli bildirim iletileri gönderir. Her ekleyerek işlemek istediğiniz iletileri işlemek için bir işlev belirtebilirsiniz bir **on_notıfy_reflect** makrosu denetim pencerenin ileti eşlemesi veya ekleyerek bir `ON_NOTIFY` makrosu üst pencerenin ileti eşlemesi için. Bkz: [ağaç denetimi bildirim iletileri](../mfc/tree-control-notification-messages.md) olası bildirimler listesi için bu konudaki sonraki.  
  
-   Denetim değerlerini ayarlamak için çeşitli kümesi üye işlevleri çağırma. Yaptığınız değişiklikler girinti ayarlama ve metin, görüntü veya bir öğesiyle ilişkilendirilmiş verileri değiştirme içerir.  
  
-   Denetimin içeriğini incelemek için çeşitli Get işlevleri kullanın. Ağaç denetimi üst, alt öğelerini ve belirtilen öğesinin eşdüzey işleyicilerine almanıza olanak sağlayan işlevler ile içeriğini de geçebilir. Düğümün alt öğelerinin belirli bile sıralayabilirsiniz.  
  
-   Denetimle bittiğinde, düzgün bir şekilde yok emin olun. Ağaç denetimi iletişim kutusudur veya bir görünüm ise, onu ve `CTreeCtrl` nesne yok otomatik olarak. Her iki denetimi emin olmak ihtiyacınız olmayan, varsa ve `CTreeCtrl` nesne düzgün yok.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

