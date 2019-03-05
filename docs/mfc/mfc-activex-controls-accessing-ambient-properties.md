---
title: 'MFC ActiveX denetimleri: Ortam özelliklerine erişme'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], accessing ambient properties
- properties [MFC], accessing ambient
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
ms.openlocfilehash: 585ec8720a654bbcb728330d70ddb914f2543e41
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57305230"
---
# <a name="mfc-activex-controls-accessing-ambient-properties"></a>MFC ActiveX denetimleri: Ortam özelliklerine erişme

Bu makalede, bir ActiveX denetimini denetim kapsayıcısının ortam özelliklerine nasıl erişebilir açıklanmaktadır.

Bir denetimi kapsayıcının ortam özellikleri erişerek kapsayıcısı hakkında bilgi edinebilirsiniz. Bu özellikler, kapsayıcının arka plan rengi, kapsayıcı şu anda kullanıcı modunda veya tasarımcı modunda olup gibi kapsayıcı ve işletimsel özelliklerine tarafından kullanılan geçerli yazı tipi gibi görsel özelliklerini ortaya çıkarır. Bir denetimin görünümünü ve davranışını gömülü belirli kapsayıcıya olarak uyarlamak için ortam özellikleri kullanabilirsiniz. Ancak, bir denetim hiçbir zaman kapsayıcısıyla herhangi belirli bir ortam özelliği desteklediğini varsaymanız gerekir. Aslında, bazı kapsayıcıları herhangi bir ortam özelliklerine hiç desteklemeyebilir. Bir çevresel özelliğe olmaması durumunda, bir denetim makul bir varsayılan değere varsaymanız gerekir.

Bir çevresel özelliğe erişmek için çağrı yapmak [COleControl::GetAmbientProperty](../mfc/reference/colecontrol-class.md#getambientproperty). Bu işlev, ortam özelliği için gönderme kimliği (dosya OLECTL. ilk parametre olarak bekliyor. H gönderme kimlikleri için standart bir ortam özellikler kümesini tanımlar).

Parametreleri `GetAmbientProperty` işlevi olan dağıtım kimliği, beklenen özellik türü ve bellek işaretçisi gösteren bir değişken etiket değeri yere yönlendirileceksiniz. Bu işaretçinin başvurduğu veri türü, değişken etikete bağlı olarak değişir. İşlev döndürür **TRUE** kapsayıcı özelliğini destekliyorsa, aksi halde döndürür **FALSE**.

Aşağıdaki kod örneğinde "Kullanıcı modu." adlı ortam özelliğin değerini alır. Özelliği varsayılan değerine kapsayıcı tarafından desteklenmiyor, **TRUE** varsayılır:

[!code-cpp[NVC_MFC_AxUI#30](../mfc/codesnippet/cpp/mfc-activex-controls-accessing-ambient-properties_1.cpp)]

Size kolaylık sağlamak için `COleControl` birçok yaygın olarak kullanılan ortam özelliklerine erişme ve özelliklerini mevcut olmadığı durumlarda uygun varsayılanlara döndürmek için yardımcı işlevleri sağlar. Bu yardımcı işlevleri aşağıdaki gibidir:

- [COleControl::AmbientBackColor](../mfc/reference/colecontrol-class.md#ambientbackcolor)

- [AmbientDisplayName](../mfc/reference/colecontrol-class.md#ambientdisplayname)

- [AmbientFont](../mfc/reference/colecontrol-class.md#ambientfont)

    > [!NOTE]
    >  Arayan çağırmalıdır `Release( )` üzerinde döndürülen yazı tipi.

- [AmbientForeColor](../mfc/reference/colecontrol-class.md#ambientforecolor)

- [AmbientLocaleID](../mfc/reference/colecontrol-class.md#ambientlocaleid)

- [AmbientScaleUnits](../mfc/reference/colecontrol-class.md#ambientscaleunits)

- [AmbientTextAlign](../mfc/reference/colecontrol-class.md#ambienttextalign)

- [AmbientUserMode](../mfc/reference/colecontrol-class.md#ambientusermode)

- [AmbientUIDead](../mfc/reference/colecontrol-class.md#ambientuidead)

- [AmbientShowHatching](../mfc/reference/colecontrol-class.md#ambientshowhatching)

- [AmbientShowGrabHandles](../mfc/reference/colecontrol-class.md#ambientshowgrabhandles)

(Bazı eylem kapsayıcının), bir ortam özelliğinin değeri değiştiğinde `OnAmbientPropertyChanged` denetimin üye işlevi çağrılır. Böyle bir bildirim işlemek için bu üye işlevini geçersiz kılar. Parametresi için `OnAmbientPropertyChanged` etkilenen ortam özelliğinin dağıtım kimliğidir. Bu dağıtım kimliği değerini gösteren bir veya daha fazla ortam özelliklerine değişti, DISPID_UNKNOWN olabilir ancak hangi özellikleri etkilenmiştir bilgileri kullanılamıyor.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)
