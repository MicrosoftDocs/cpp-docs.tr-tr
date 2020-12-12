---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: olaylar'
title: 'MFC ActiveX Denetimleri: Olaylar'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], events
- notifications [MFC], notifying containers of events
- custom events [MFC], adding to ActiveX controls
- events [MFC], mapping
- COleControl class [MFC], handling of events
- mappings [MFC], events
- stock events [MFC]
- container events [MFC]
- events [MFC], ActiveX controls
- OLE events [MFC]
ms.assetid: e1e57e0c-206b-4923-a0b5-682c26564f74
ms.openlocfilehash: 8a360931287432e9f0ee0fc55e7e5120bcbd390f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240695"
---
# <a name="mfc-activex-controls-events"></a>MFC ActiveX Denetimleri: Olaylar

ActiveX denetimleri, bir kapsayıcıya bir şeyin oluştuğunu bildiren olayları bildirir. Yaygın olay örnekleri, denetime tıklamalar, klavye kullanılarak girilen veriler ve denetimin durumundaki değişiklikler içerir. Bu eylemler gerçekleştiğinde, denetim kapsayıcıyı uyarmak için bir olay harekete geçirilir.

Olaylar da iletiler olarak adlandırılır.

MFC iki tür olayı destekler: stok ve özel. Hisse senedi olayları, sınıf [Coelcontrol](reference/colecontrol-class.md) 'un otomatik olarak işlediği olaylardır. Hisse senedi olaylarının tamamı listesi için [MFC ActiveX denetimleri: stok olayları ekleme](mfc-activex-controls-adding-stock-events-to-an-activex-control.md)makalesine bakın. Özel olaylar, bu denetime özgü bir eylem gerçekleştiğinde, bir denetimin kapsayıcıya bildirme yeteneği sağlar. Bazı örnekler, bir denetimin veya belirli bir pencere iletisinin iç durumunda bir değişiklik olabilir.

Denetiminizin olayları düzgün bir şekilde tetiklemesi için denetim sınıfınızın her bir olayını ilgili olay gerçekleştiğinde çağrılması gereken bir üye işlevle eşleşmesi gerekir. Bu eşleme mekanizması (olay haritası denir) olay hakkında bilgi toplar ve Visual Studio 'Nun denetim olaylarına kolayca erişmesini ve bunları işlemesini sağlar. Bu olay eşlemesi, üst bilgisinde bulunan aşağıdaki makro tarafından bildirilmiştir (. H) denetim sınıfı bildiriminin dosyası:

[!code-cpp[NVC_MFC_AxUI#2](codesnippet/cpp/mfc-activex-controls-events_1.h)]

Olay eşlemesi bildirildiğinde, denetimin uygulamasında tanımlanmalıdır (. CPP) dosyası. Aşağıdaki kod satırları olay haritasını tanımlar ve denetiminizin belirli olayları başlatmasına izin verir:

[!code-cpp[NVC_MFC_AxUI#3](codesnippet/cpp/mfc-activex-controls-events_2.cpp)]
[!code-cpp[NVC_MFC_AxUI#4](codesnippet/cpp/mfc-activex-controls-events_3.cpp)]

Projeyi oluşturmak için MFC ActiveX Denetim Sihirbazı 'nı kullanırsanız, bu satırları otomatik olarak ekler. MFC ActiveX Denetim Sihirbazı 'nı kullanmıyorsanız, bu satırları el ile eklemeniz gerekir.

Sınıf Görünümü, sınıfının desteklediği stok olaylarını `COleControl` veya tanımladığınız özel olayları ekleyebilirsiniz. Her yeni olay için, Sınıf Görünümü otomatik olarak denetimin olay haritasına ve denetimin öğesine doğru girişi ekler. IDL dosyası.

Diğer iki makale de olayları ayrıntılı olarak ele almaktadır:

- [MFC ActiveX denetimleri: stok olayları ekleme](mfc-activex-controls-adding-stock-events-to-an-activex-control.md)

- [MFC ActiveX denetimleri: özel olaylar ekleme](mfc-activex-controls-adding-custom-events.md)

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)<br/>
[MFC ActiveX denetimleri: Yöntemler](mfc-activex-controls-methods.md)<br/>
[Coelcontrol sınıfı](reference/colecontrol-class.md)
