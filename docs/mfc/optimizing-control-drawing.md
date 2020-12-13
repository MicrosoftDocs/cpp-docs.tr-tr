---
description: 'Daha fazla bilgi edinin: denetim çizimini Iyileştirme'
title: Denetim Çizimini İyileştirme
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
ms.openlocfilehash: 93e948d4a572f4e02c8676b2af1b6f8943004f26
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331813"
---
# <a name="optimizing-control-drawing"></a>Denetim Çizimini İyileştirme

Bir denetimin kendisini kapsayıcı tarafından sağlanan bir cihaz bağlamına çizmesi istendiğinde, genellikle GDI nesnelerini (örneğin, kalemler, fırçalar ve yazı tipleri) cihaz bağlamına seçer, çizim işlemlerini gerçekleştirir ve önceki GDI nesnelerini geri yükler. Kapsayıcıda aynı cihaz bağlamına çizilmek üzere birden çok denetim varsa ve her denetim gereken GDI nesnelerini seçerse, denetimler önceden seçili nesneleri tek tek geri yüklemediyseniz, zaman kaydedilebilir. Tüm denetimler çizildikten sonra kapsayıcı özgün nesneleri otomatik olarak geri yükleyebilir.

Bir kapsayıcının bu tekniği destekleyip desteklemediğini algılamak için, bir denetim [Colicontrol:: IsOptimizedDraw](reference/colecontrol-class.md#isoptimizeddraw) üye işlevini çağırabilir. Bu işlev **true** değerini döndürürse denetim, daha önce seçilen nesneleri geri yüklemenin normal adımını atlayabilir.

Aşağıdaki (iyileştirilmemiş) işleve sahip bir denetim düşünün `OnDraw` :

[!code-cpp[NVC_MFC_AxOpt#15](codesnippet/cpp/optimizing-control-drawing_1.cpp)]

Bu örnekteki kalem ve fırça yerel değişkenlerdir, yani Yıkıcılar kapsam dışına çıkar ( `OnDraw` işlev sona erdiğinde) çağrılır. Yok ediciler ilgili GDI nesnelerini silmeye çalışır. Ancak, ' den geri dönme sırasında onları cihaz bağlamında bırakmayı planlıyorsanız silinmemelidir `OnDraw` .

Tamamlandığında, [CPen](reference/cpen-class.md) ve [CBrush](reference/cbrush-class.md) nesnelerinin yok edilmesi için `OnDraw` bunları yerel değişkenler yerine üye değişkenlerde saklayın. Denetimin sınıf bildiriminde, iki yeni üye değişkeni için bildirim ekleyin:

[!code-cpp[NVC_MFC_AxOpt#16](codesnippet/cpp/optimizing-control-drawing_2.h)]
[!code-cpp[NVC_MFC_AxOpt#17](codesnippet/cpp/optimizing-control-drawing_3.h)]

Sonra, `OnDraw` işlev aşağıdaki şekilde yeniden yazılabilir:

[!code-cpp[NVC_MFC_AxOpt#18](codesnippet/cpp/optimizing-control-drawing_4.cpp)]

Bu yaklaşım her seferinde kalemin ve fırçanın oluşturulmasını önler `OnDraw` . Hız geliştirmesi, ek örnek verilerinin bakımının maliyetiyle gelir.

ForeColor veya BackColor özelliği değişirse, kalemin veya fırçanın yeniden oluşturulması gerekir. Bunu yapmak için [OnForeColorChanged](reference/colecontrol-class.md#onforecolorchanged) ve [OnBackColorChanged](reference/colecontrol-class.md#onbackcolorchanged) üye işlevlerini geçersiz kılın:

[!code-cpp[NVC_MFC_AxOpt#19](codesnippet/cpp/optimizing-control-drawing_5.cpp)]

Son olarak, gereksiz çağrıları ortadan kaldırmak için `SelectObject` `OnDraw` aşağıdaki gibi değiştirin:

[!code-cpp[NVC_MFC_AxOpt#20](codesnippet/cpp/optimizing-control-drawing_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri: Iyileştirme](mfc-activex-controls-optimization.md)<br/>
[Coelcontrol sınıfı](reference/colecontrol-class.md)<br/>
[MFC ActiveX denetimleri](mfc-activex-controls.md)<br/>
[MFC ActiveX denetimi Sihirbazı](reference/mfc-activex-control-wizard.md)<br/>
[MFC ActiveX denetimleri: ActiveX denetimini boyama](mfc-activex-controls-painting-an-activex-control.md)
