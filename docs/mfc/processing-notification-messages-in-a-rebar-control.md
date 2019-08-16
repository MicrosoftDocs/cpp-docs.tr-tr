---
title: Bir Rebar Denetiminde Bildirim İletilerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
ms.openlocfilehash: 948990c8597c2ccdcec496252c6801c02a78cbf5
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/15/2019
ms.locfileid: "69507953"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Bir Rebar Denetiminde Bildirim İletilerini İşleme

Rebar denetiminin üst sınıfında, işlemek istediğiniz herhangi bir Rebar `OnChildNotify` Control (`CReBarCtrl`) bildirim iletisi için Switch ifadesiyle bir işleyici işlevi oluşturun. Kullanıcı, nesneleri yeniden çubuk denetimi üzerine sürüklediğinde, yeniden çubuk bantların yerleşimini değiştirdiğinde, yeniden çubuk denetiminden bantları sildiği ve bu şekilde devam eden bildirimler üst pencereye gönderilir.

Aşağıdaki bildirim iletileri, Rebar denetim nesnesi tarafından gönderilebilir:

- Yeniden çubuk kendini otomatik olarak yeniden boyutlandırdığında bir Rebar denetimi tarafından gönderilen (RBS_AUTOSIZE stiliyle oluşturulan) RBN_AUTOSIZE.

- Kullanıcı bir bandı sürüklemeye başladığında bir Rebar denetimi tarafından gönderilen RBN_BEGINDRAG.

- Bir bandın alt penceresi yeniden boyutlandırılırken bir Rebar denetimi tarafından gönderilen RBN_CHILDSIZE.

- RBN_DELETEDBAND bir bant silindikten sonra bir Rebar denetimi tarafından gönderilir.

- Bir bant silinmek üzere olduğunda bir Rebar denetimi tarafından gönderilen RBN_DELETINGBAND.

- RBN_ENDDRAG, Kullanıcı bir bandı sürüklemeyi kestiğinde bir Rebar denetimi tarafından gönderilir.

- Bir nesne denetimdeki bir bandı üzerine sürüklendiğinde bir Rebar denetimi tarafından gönderilen (RBS_REGISTERDROP stiliyle oluşturulan) RBN_GETOBJECT.

- RBN_HEIGHTCHANGE, yüksekliği değiştiğinde bir Rebar denetimi tarafından gönderilir.

- RBN_LAYOUTCHANGED, Kullanıcı denetimin bantların yerleşimini değiştirdiğinde bir Rebar denetimi tarafından gönderilir.

Bu bildirimler hakkında daha fazla bilgi için bkz. Windows SDK [Rebar Control Reference](/windows/win32/controls/rebar-control-reference) .

## <a name="see-also"></a>Ayrıca bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
