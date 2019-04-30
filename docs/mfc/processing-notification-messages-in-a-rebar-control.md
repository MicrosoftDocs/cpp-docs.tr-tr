---
title: Bir Rebar Denetiminde Bildirim İletilerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
ms.openlocfilehash: 8ac225802bd1d0a0a4b0f30e017fa677f1072fd3
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/24/2019
ms.locfileid: "64339634"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Bir Rebar Denetiminde Bildirim İletilerini İşleme

Çubuk barınağı denetiminin üst sınıfta oluşturma bir `OnChildNotify` switch deyimi için herhangi bir çubuk barınağı denetimi işleyicisi işlevini (`CReBarCtrl`) bildirim iletilerini işlemek istediğiniz. Kullanıcı çubuk barınağı şeritleri siler rebar bantları düzenini çubuk barınağı şeritleri ve benzeri bantları değişiklikleri nesneleri sürüklediğinde bildirimleri üst pencereye gönderilir.

Aşağıdaki bildirim iletileri çubuk barınağı denetimi nesne tarafından gönderilebilecek:

- RBN_AUTOSIZE gönderilen (RBS_AUTOSIZE stiliyle oluşturan) bir çubuk barınağı denetimi tarafından ne zaman çubuk barınağı otomatik olarak yeniden boyutlandırır kendisi.

- RBN_BEGINDRAG kullanıcı bir bant sürükleme işlemi başladığında, bir çubuk barınağı denetimi tarafından gönderilir.

- RBN_CHILDSIZE bir bandın çocuk penceresi yeniden boyutlandırıldığında bir çubuk barınağı denetimi tarafından gönderilir.

- RBN_DELETEDBAND bir bant silindikten sonra bir çubuk barınağı denetimi tarafından gönderilir.

- RBN_DELETINGBAND bir bant silinmek üzere olduğunda bir çubuk barınağı denetimi tarafından gönderilir.

- RBN_ENDDRAG kullanıcı bir bant sürükleyerek durdurulduğunda bir çubuk barınağı denetimi tarafından gönderilir.

- RBN_GETOBJECT gönderilen (RBS_REGISTERDROP stiliyle oluşturan) bir çubuk barınağı denetimi tarafından ne zaman bir nesne sürüklediğiniz denetiminde bir bant üzerinde.

- RBN_HEIGHTCHANGE yükseklik değiştiğinde bir çubuk barınağı denetimi tarafından gönderilir.

- RBN_LAYOUTCHANGED kullanıcı denetiminin bantları düzenini değiştirdiği zaman bir çubuk barınağı denetimi tarafından gönderilir.

Bu bildirimleri hakkında daha fazla bilgi için bkz. [Rebar denetimi başvuru](/windows/desktop/controls/rebar-control-reference) Windows SDK.

## <a name="see-also"></a>Ayrıca bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
