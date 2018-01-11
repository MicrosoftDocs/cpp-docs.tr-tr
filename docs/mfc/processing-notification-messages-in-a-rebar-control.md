---
title: "Bir Rebar denetiminde bildirim iletilerini işleme | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22a8b584c309cd6698ddd73449fcbba866111190
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Bir Rebar Denetiminde Bildirim İletilerini İşleme
Rebar denetimiyle üst sınıf oluşturmak bir `OnChildNotify` herhangi bir rebar denetimi için bir anahtar ifadesiyle işleyici işlevi (`CReBarCtrl`) bildirim iletilerini işlemek istediğiniz. Kullanıcı siler rebar bantları düzenini rebar denetiminden ve benzeri bantları değişiklikleri rebar denetimi nesneleri sürüklendiğinde bildirimleri üst penceresine gönderilir.  
  
 Aşağıdaki bildirim iletileri rebar denetimi nesne tarafından gönderilebilir:  
  
-   **RBN_AUTOSIZE** rebar denetimi tarafından gönderilen (ile oluşturulan **RBS_AUTOSIZE** stili) ne zaman rebar otomatik olarak yeniden boyutlandırır kendisi.  
  
-   **RBN_BEGINDRAG** kullanıcı bir bant sürükleyerek başladığında rebar denetimi tarafından gönderilir.  
  
-   **RBN_CHILDSIZE** bir bant ait alt pencere yeniden boyutlandırıldığında rebar denetimi tarafından gönderilir.  
  
-   **RBN_DELETEDBAND** bir rebar denetiminde bir bant silindikten sonra gönderilir.  
  
-   **RBN_DELETINGBAND** bir rebar denetiminde bir bant silinmek üzere olduğunda gönderilir.  
  
-   **RBN_ENDDRAG** kullanıcı bir bant sürükleyerek durduğunda rebar denetimi tarafından gönderilir.  
  
-   **RBN_GETOBJECT** rebar denetimi tarafından gönderilen (ile oluşturulan **RBS_REGISTERDROP** stili) bir nesne zaman sürüklenen denetiminde bir bant üzerinde.  
  
-   **RBN_HEIGHTCHANGE** yüksekliği değiştiğinde rebar denetimi tarafından gönderilen.  
  
-   **RBN_LAYOUTCHANGED** kullanıcı denetimin bantları Düzen değiştirdiğinde rebar denetimi tarafından gönderilir.  
  
 Bu bildirimleri hakkında daha fazla bilgi için bkz: [Rebar denetimi başvurusu](http://msdn.microsoft.com/library/windows/desktop/bb774375) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CReBarCtrl kullanma](../mfc/using-crebarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

