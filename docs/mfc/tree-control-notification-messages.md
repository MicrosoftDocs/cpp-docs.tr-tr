---
title: "Ağaç denetimi bildirim iletileri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- notifications [MFC], tree controls
- messages [MFC], notification
- CTreeCtrl class [MFC], notifications
- notifications [MFC], CTreeCtrl
- tree controls [MFC], notification messages
ms.assetid: ac7013b4-91dd-4668-bd75-439ca0680ef9
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 60552547087ce97a92429c94654238f9c7d2870c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="tree-control-notification-messages"></a>Ağaç Denetimi Bildirim İletileri
Ağaç denetimi ([CTreeCtrl](../mfc/reference/ctreectrl-class.md)) olarak aşağıdaki bildirim iletileri gönderir **wm_notıfy** iletileri:  
  
|Bildirim iletisi|Açıklama|  
|--------------------------|-----------------|  
|**TVN_BEGINDRAG**|Sürükle ve bırak işlemi başlangıcı işaret eder|  
|**TVN_BEGINLABELEDIT**|Yerinde etiket düzenleme başlangıcı işaret eder|  
|**TVN_BEGINRDRAG**|Farenin sağ düğmesiyle bir Sürükle ve bırak işlemi başlangıcı işaret eder|  
|**TVN_DELETEITEM**|Belirli bir öğeyi silme işaret eder|  
|**TVN_ENDLABELEDIT**|Etiket düzenleme sonu işaret eder|  
|**TVN_GETDISPINFO**|Ağaç denetimi öğeyi görüntülemek için gerektirdiği istekleri bilgiler|  
|**TVN_ITEMEXPANDED**|Bir üst öğenin alt öğeleri listesi genişletilmiş veya daraltılmış olduğunu sinyalleri|  
|**TVN_ITEMEXPANDING**|Bir üst öğenin alt öğeleri hakkında genişletilmiş veya daraltılmış listesidir sinyalleri|  
|**TVN_KEYDOWN**|Klavye olay işaret eder|  
|**TVN_SELCHANGED**|Seçimi bir öğe başka değişti sinyalleri|  
|**TVN_SELCHANGING**|Bir öğeden diğerine değiştirilmek üzere seçimdir sinyalleri|  
|**TVN_SETDISPINFO**|Bir öğe için tutulan bilgileri güncelleştirmek için bildirim|  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CTreeCtrl kullanma](../mfc/using-ctreectrl.md)   
 [Denetimleri](../mfc/controls-mfc.md)

