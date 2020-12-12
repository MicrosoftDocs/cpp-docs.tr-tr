---
description: 'Daha fazla bilgi edinin: MFC ActiveX denetimleri: ortam özelliklerine erişme'
title: 'MFC ActiveX Denetimleri: Ortam Özelliklerine Erişme'
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], accessing ambient properties
- properties [MFC], accessing ambient
ms.assetid: fdc9db29-e6b0-45d2-a879-8bd60e2058a7
ms.openlocfilehash: 6b553c73873a6f96cab3ab55b576a51045c06609
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97203074"
---
# <a name="mfc-activex-controls-accessing-ambient-properties"></a>MFC ActiveX Denetimleri: Ortam Özelliklerine Erişme

Bu makalede, bir ActiveX denetiminin denetim kapsayıcısının çevresel özelliklerine nasıl erişebileceği açıklanır.

Bir Denetim kapsayıcının çevresel özelliklerine erişerek kapsayıcısı hakkında bilgi alabilir. Bu özellikler, kapsayıcının arka plan rengi, kapsayıcı tarafından kullanılan geçerli yazı tipi ve kapsayıcının Kullanıcı modu ya da tasarımcı modunda olup olmadığı gibi işletimsel özellikler gibi görsel özellikleri sunar. Bir denetim, görünüm ve davranışını gömülü olduğu belirli bir kapsayıcıya uyarlamak için çevresel özellikleri kullanabilir. Ancak, bir Denetim kapsayıcının belirli bir çevresel özelliği desteklediğini asla varsaymamalıdır. Aslında bazı kapsayıcılar hiçbir çevresel özelliği desteklemeyebilir. Çevresel Özellik yokluğunda denetim, makul bir varsayılan değeri varsaymalıdır.

Bir çevresel özelliğe erişmek için [Coelcontrol:: Getambentproperty](reference/colecontrol-class.md#getambientproperty)' a bir çağrı yapın. Bu işlev, ortam özelliğinin dağıtım KIMLIĞINI ilk parametre olarak bekler (OLECTL dosyası. H standart çevresel özellikler kümesi için dağıtım kimliklerini tanımlar).

`GetAmbientProperty`İşlevin parametreleri, DAĞıTıM kimliğidir, beklenen özellik türünü belirten bir varyant etiketi ve değerin döndürülmesi gereken bir bellek işaretçisi. Bu işaretçinin başvurduğu verilerin türü, varyant etiketine göre değişir. Kapsayıcı özelliği destekliyorsa, işlev **true** değerini döndürür, aksi takdirde **false** döndürür.

Aşağıdaki kod örneği, "Kullanıcı adı" adlı çevresel özelliğin değerini edinir. Özelliği kapsayıcı tarafından desteklenmiyorsa, varsayılan **true** değeri varsayılır:

[!code-cpp[NVC_MFC_AxUI#30](codesnippet/cpp/mfc-activex-controls-accessing-ambient-properties_1.cpp)]

Kolaylık olması için, `COleControl` yaygın olarak kullanılan çevresel özelliklerden birçoğuna erişen ve özellikler kullanılabilir olmadığında uygun Varsayılanları döndüren yardımcı işlevler sağlar. Bu yardımcı işlevler aşağıdaki gibidir:

- [Coelcontrol:: AmbientBackColor](reference/colecontrol-class.md#ambientbackcolor)

- [AmbientDisplayName](reference/colecontrol-class.md#ambientdisplayname)

- [AmbientFont](reference/colecontrol-class.md#ambientfont)

    > [!NOTE]
    >  Çağıran `Release( )` , döndürülen yazı tipiyle çağırmalıdır.

- [AmbientForeColor](reference/colecontrol-class.md#ambientforecolor)

- [AmbientLocaleID](reference/colecontrol-class.md#ambientlocaleid)

- [AmbientScaleUnits](reference/colecontrol-class.md#ambientscaleunits)

- [AmbientTextAlign](reference/colecontrol-class.md#ambienttextalign)

- [AmbientUserMode](reference/colecontrol-class.md#ambientusermode)

- [AmbientUIDead](reference/colecontrol-class.md#ambientuidead)

- [AmbientShowHatching](reference/colecontrol-class.md#ambientshowhatching)

- [AmbientShowGrabHandles](reference/colecontrol-class.md#ambientshowgrabhandles)

Bir ortam özelliğinin değeri değişirse (kapsayıcının bazı eylemleri aracılığıyla), `OnAmbientPropertyChanged` denetimin üye işlevi çağırılır. Bu tür bir bildirimi işlemek için bu üye işlevini geçersiz kılın. Parametresi, `OnAmbientPropertyChanged` etkilenen çevresel özelliğin DAĞıTıM kimliğidir. Bu dağıtım KIMLIĞININ değeri, bir veya daha fazla çevresel özelliklerin değiştiğini gösteren DISPID_UNKNOWN olabilir, ancak hangi özelliklerin etkilendiğine ilişkin bilgi kullanılamaz.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri](mfc-activex-controls.md)
