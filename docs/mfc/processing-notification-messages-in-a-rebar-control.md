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
ms.openlocfilehash: dce09e84e9a2b5262d05847746f819a122ec36c5
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43208981"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Bir Rebar Denetiminde Bildirim İletilerini İşleme
Çubuk barınağı denetiminin üst sınıfta oluşturma bir `OnChildNotify` switch deyimi için herhangi bir çubuk barınağı denetimi işleyicisi işlevini (`CReBarCtrl`) bildirim iletilerini işlemek istediğiniz. Kullanıcı çubuk barınağı şeritleri siler rebar bantları düzenini çubuk barınağı şeritleri ve benzeri bantları değişiklikleri nesneleri sürüklediğinde bildirimleri üst pencereye gönderilir.  
  
 Aşağıdaki bildirim iletileri çubuk barınağı denetimi nesne tarafından gönderilebilecek:  
  
-   RBN_AUTOSIZE gönderilen (RBS_AUTOSIZE stiliyle oluşturan) bir çubuk barınağı denetimi tarafından ne zaman çubuk barınağı otomatik olarak yeniden boyutlandırır kendisi.  
  
-   RBN_BEGINDRAG kullanıcı bir bant sürükleme işlemi başladığında, bir çubuk barınağı denetimi tarafından gönderilir.  
  
-   RBN_CHILDSIZE bir bandın çocuk penceresi yeniden boyutlandırıldığında bir çubuk barınağı denetimi tarafından gönderilir.  
  
-   RBN_DELETEDBAND bir bant silindikten sonra bir çubuk barınağı denetimi tarafından gönderilir.  
  
-   RBN_DELETINGBAND bir bant silinmek üzere olduğunda bir çubuk barınağı denetimi tarafından gönderilir.  
  
-   RBN_ENDDRAG kullanıcı bir bant sürükleyerek durdurulduğunda bir çubuk barınağı denetimi tarafından gönderilir.  
  
-   RBN_GETOBJECT gönderilen (RBS_REGISTERDROP stiliyle oluşturan) bir çubuk barınağı denetimi tarafından ne zaman bir nesne sürüklediğiniz denetiminde bir bant üzerinde.  
  
-   RBN_HEIGHTCHANGE yükseklik değiştiğinde bir çubuk barınağı denetimi tarafından gönderilir.  
  
-   RBN_LAYOUTCHANGED kullanıcı denetiminin bantları düzenini değiştirdiği zaman bir çubuk barınağı denetimi tarafından gönderilir.  
  
 Bu bildirimleri hakkında daha fazla bilgi için bkz. [Rebar denetimi başvuru](https://msdn.microsoft.com/library/windows/desktop/bb774375) Windows SDK.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CReBarCtrl kullanma](../mfc/using-crebarctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

