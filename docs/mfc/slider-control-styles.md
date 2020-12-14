---
description: 'Daha fazla bilgi edinin: kaydırıcı denetim stilleri'
title: Kaydırıcı Denetim Stilleri
ms.date: 11/04/2016
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
ms.openlocfilehash: cec057683862212a4d999ec7d0488c5f2a0837cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216918"
---
# <a name="slider-control-styles"></a>Kaydırıcı Denetim Stilleri

Kaydırıcı denetimleri ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) dikey ya da yatay yönlendirmeye sahip olabilir. Her iki taraftan birinde değer çizgisi veya hiçbiri olabilir. Ardışık değerler aralığını belirtmek için de kullanılabilir. Bu özellikler kaydırıcı denetimini oluştururken belirttiğiniz kaydırıcı denetim stilleri kullanılarak denetlenir.

TBS_HORZ ve TBS_VERT stilleri kaydırıcı denetiminin yönünü belirlenir. Bir yön belirtmezseniz, kaydırıcı denetimi yatay olarak yönelimlidir.

TBS_AUTOTICKS stili, değer aralığındaki her artış için değer işaretine sahip bir kaydırıcı denetimi oluşturur. Bu değer çizgileri, [SetRange](../mfc/reference/csliderctrl-class.md#setrange) üye işlevini çağırdığınızda otomatik olarak eklenir. TBS_AUTOTICKS belirtmezseniz, değer çizgilerinin konumlarını belirtmek için [SetTic](../mfc/reference/csliderctrl-class.md#settic) ve [setticde](../mfc/reference/csliderctrl-class.md#setticfreq)gibi üye işlevlerini kullanabilirsiniz. Değer çizgilerini göstermez kaydırıcı denetimi oluşturmak için TBS_NOTICKS stilini kullanabilirsiniz.

Kaydırıcı denetiminin her iki tarafında da değer çizgilerini görüntüleyebilirsiniz. Yatay kaydırıcı denetimleri için TBS_BOTTOM veya TBS_TOP stilini belirtebilirsiniz. Dikey kaydırıcı denetimleri için TBS_RIGHT veya TBS_LEFT stilini belirtebilirsiniz. (TBS_BOTTOM ve TBS_RIGHT varsayılan ayarlardır.) Herhangi bir yöndeki kaydırıcı denetiminin her iki tarafındaki onay işaretleri için TBS_BOTH stilini belirtin.

Kaydırıcı denetimi yalnızca, oluşturduğunuzda TBS_ENABLESELRANGE stili belirtirseniz bir seçim aralığı gösterebilir. Kaydırıcı denetiminde bu stil varsa, seçim aralığının başlangıç ve bitiş konumlarındaki değer çizgileri, üçgen (dikey tireler yerine) olarak görüntülenir ve seçim aralığı vurgulanır. Örneğin, seçim aralıkları basit bir zamanlama uygulamasında yararlı olabilir. Kullanıcı, zamanlanan bir toplantı zamanının belirlenmesi için bir gündeki saatlere karşılık gelen bir dizi onay işareti seçebilir.

Varsayılan olarak, bir kaydırıcı denetiminin kaydırıcısının uzunluğu seçim aralığı değiştikçe değişir. Kaydırıcı denetiminin TBS_FIXEDLENGTH stili varsa, seçim aralığı değişse bile kaydırıcının uzunluğu aynı kalır. TBS_NOTHUMB stili olan kaydırıcı denetimi kaydırıcı içermez.

## <a name="see-also"></a>Ayrıca bkz.

[CSliderCtrl Kullanma](../mfc/using-csliderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
