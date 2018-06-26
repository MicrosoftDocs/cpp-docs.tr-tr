---
title: Bir Rebar denetiminde bildirim iletilerini işleme | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9a1d42d129ab7b7d2e98ae1126b8f32f68b1f356
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/25/2018
ms.locfileid: "36931833"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Bir Rebar Denetiminde Bildirim İletilerini İşleme
Rebar denetimiyle üst sınıf oluşturmak bir `OnChildNotify` herhangi bir rebar denetimi için bir anahtar ifadesiyle işleyici işlevi (`CReBarCtrl`) bildirim iletilerini işlemek istediğiniz. Kullanıcı siler rebar bantları düzenini rebar denetiminden ve benzeri bantları değişiklikleri rebar denetimi nesneleri sürüklendiğinde bildirimleri üst penceresine gönderilir.  
  
 Aşağıdaki bildirim iletileri rebar denetimi nesne tarafından gönderilebilir:  
  
-   Rebar denetimiyle (RBS_AUTOSIZE stiliyle oluşturulan) tarafından gönderilen RBN_AUTOSIZE zaman rebar otomatik olarak yeniden boyutlandırır kendisi.  
  
-   Kullanıcı bir bant sürükleyerek başladığında rebar denetimi tarafından gönderilen RBN_BEGINDRAG.  
  
-   Bir bant ait alt pencere yeniden boyutlandırıldığında rebar denetimi tarafından gönderilen RBN_CHILDSIZE.  
  
-   Bir bant silindikten sonra rebar denetimi tarafından gönderilen RBN_DELETEDBAND.  
  
-   Bir bant silinmek üzere olduğunda rebar denetimi tarafından gönderilen RBN_DELETINGBAND.  
  
-   Kullanıcı bir bant sürükleyerek durduğunda rebar denetimi tarafından gönderilen RBN_ENDDRAG.  
  
-   Rebar denetimiyle (RBS_REGISTERDROP stiliyle oluşturulan) tarafından gönderilen RBN_GETOBJECT bir nesne zaman sürüklenen denetiminde bir bant üzerinde.  
  
-   RBN_HEIGHTCHANGE yüksekliği değiştiğinde rebar denetimi tarafından gönderilen.  
  
-   RBN_LAYOUTCHANGED kullanıcı denetimin bantları Düzen değiştirdiğinde rebar denetimi tarafından gönderilen.  
  
 Bu bildirimleri hakkında daha fazla bilgi için bkz: [Rebar denetimi başvurusu](http://msdn.microsoft.com/library/windows/desktop/bb774375) Windows SDK'sındaki.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CReBarCtrl kullanma](../mfc/using-crebarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

