---
description: 'Daha fazla bilgi edinin: bir Rebar denetiminde bildirim Iletilerini Işleme'
title: Bir Rebar Denetiminde Bildirim İletilerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
ms.openlocfilehash: 6255f10068072f75f556cf1c8576008ab821ed27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97154844"
---
# <a name="processing-notification-messages-in-a-rebar-control"></a>Bir Rebar Denetiminde Bildirim İletilerini İşleme

Rebar denetiminin üst sınıfında, `OnChildNotify` işlemek istediğiniz herhangi bir Rebar Control ( `CReBarCtrl` ) bildirim iletisi için Switch ifadesiyle bir işleyici işlevi oluşturun. Kullanıcı, nesneleri yeniden çubuk denetimi üzerine sürüklediğinde, yeniden çubuk bantların yerleşimini değiştirdiğinde, yeniden çubuk denetiminden bantları sildiği ve bu şekilde devam eden bildirimler üst pencereye gönderilir.

Aşağıdaki bildirim iletileri, Rebar denetim nesnesi tarafından gönderilebilir:

- Yeniden çubuk kendini otomatik olarak yeniden boyutlandırdığında bir Rebar denetimi tarafından gönderilen RBN_AUTOSIZE (RBS_AUTOSIZE stiliyle oluşturulur).

- Kullanıcı bir bandı sürüklemeye başladığında bir Rebar denetimi tarafından gönderilen RBN_BEGINDRAG.

- Bir bandın alt penceresi yeniden boyutlandırılırken bir Rebar denetimi tarafından gönderilen RBN_CHILDSIZE.

- Bir bant silindikten sonra bir Rebar denetimi tarafından gönderilen RBN_DELETEDBAND.

- Bir bant silinmek üzere olduğunda bir Rebar denetimi tarafından gönderilen RBN_DELETINGBAND.

- Kullanıcı bir bandı sürüklemeyi kestiğinde bir Rebar denetimi tarafından gönderilen RBN_ENDDRAG.

- Bir nesne denetimdeki bir bantta sürüklendiğinde bir Rebar denetimi (RBS_REGISTERDROP stiliyle oluşturulur) tarafından RBN_GETOBJECT.

- Yüksekliği değiştirildiğinde bir Rebar denetimi tarafından gönderilen RBN_HEIGHTCHANGE.

- Kullanıcı denetim bantların yerleşimini değiştirdiğinde bir Rebar denetimi tarafından gönderilen RBN_LAYOUTCHANGED.

Bu bildirimler hakkında daha fazla bilgi için bkz. Windows SDK [Rebar Control Reference](/windows/win32/controls/rebar-control-reference) .

## <a name="see-also"></a>Ayrıca bkz.

[CReBarCtrl Kullanma](using-crebarctrl.md)<br/>
[Denetimler](controls-mfc.md)
