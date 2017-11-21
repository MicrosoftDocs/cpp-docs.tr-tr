---
title: "Ağaç denetimi etiketini düzenleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- editing tree control labels
- CTreeCtrl class [MFC], editing labels
- label editing in CTreeCtrl class [MFC]
- tree controls [MFC], label editing
ms.assetid: 6cde2ac3-43ee-468f-bac2-cf1a228ad32d
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c46616914f9cf6d1069702c16cdd03f272d6561c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="tree-control-label-editing"></a>Ağaç Denetimi Etiketini Düzenleme
Kullanıcı ağaç denetimindeki öğeleri etiketleri doğrudan düzenleyebilirsiniz ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) olan **TVS_EDITLABELS** stili. Kullanıcı odaklı öğenin etiketini tıklatarak düzenleme başlar. Bir uygulama kullanarak düzenleme başlar [EditLabel](../mfc/reference/ctreectrl-class.md#editlabel) üye işlevi. Ağaç denetimi bildirim düzenlerken başlar ve ne zaman, iptal tamamlandı veya gönderir. Düzenleme tamamlandığında, uygunsa, öğenin etiketi güncelleştirmek için sorumludur.  
  
 Etiket düzenleme başladığı, ağaç denetimi gönderir bir [TVN_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506) bildirim iletisi. Bu bildirim işleyerek bazı etiketlerini düzenleme izni ve diğer düzenleme engelleyebilirsiniz. 0 döndürme düzenleme olanağı sağlar ve sıfır olmayan döndürme engeller.  
  
 Ağaç denetimi etiketini düzenleme tamamlandı ya da iptal edildiğinde, gönderen bir [TVN_ENDLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773515) bildirim iletisi. `lParam` Parametredir adresini bir [NMTVDISPINFO](http://msdn.microsoft.com/library/windows/desktop/bb773418) yapısı. **Öğesi** üye olduğu bir [TVITEM](http://msdn.microsoft.com/library/windows/desktop/bb773456) öğesi tanımlar ve düzenlenmiş metni içeren yapısı. Öğenin etiketi, uygunsa, belki de düzenlenen dize doğrulamadan sonra güncelleştirmek için sorumlu. **PszText** üyesi `TV_ITEM` düzenlemeyi iptal ederseniz 0'dır.  
  
 Etiket, genellikle yanıt olarak düzenleme sırasında [TVN_BEGINLABELEDIT](http://msdn.microsoft.com/library/windows/desktop/bb773506) bildirim iletisini kullanarak etiketi düzenlemek için kullanılan düzenleme denetimine işaretçi alabilirsiniz [GetEditControl](../mfc/reference/ctreectrl-class.md#geteditcontrol) üyesi işlev. Düzenle denetim çağırabilirsiniz [SetLimitText](../mfc/reference/cedit-class.md#setlimittext) bir kullanıcının girebileceği metin ya da alt müdahale ve geçersiz karakterler atmak için düzenleme denetimi miktarını sınırlamak için üye işlevi. Ancak, düzenleme denetimi yalnızca görüntülendiğine dikkat edin *sonra* **TVN_BEGINLABELEDIT** gönderilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

