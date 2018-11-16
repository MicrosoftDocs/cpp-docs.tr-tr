---
title: Bir Rebar Denetiminde Bildirim İletilerini İşleme
ms.date: 11/04/2016
helpviewer_keywords:
- RBN_ notification messages, description of
- CReBarCtrl class [MFC], notification messages sent by
- RBN_ notification messages [MFC]
- notifications [MFC], CReBarCtrl
ms.assetid: 40f43a60-0c18-4d8d-8fab-213a095624f9
ms.openlocfilehash: 4c35a1efb1c93aecf17e8f57b9e96c033aa4334a
ms.sourcegitcommit: b032daf81cb5fdb1f5a988277ee30201441c4945
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/15/2018
ms.locfileid: "51693190"
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

## <a name="see-also"></a>Ayrıca Bkz.

[CReBarCtrl Kullanma](../mfc/using-crebarctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)

