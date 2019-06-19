---
title: Denetim Çizimini İyileştirme
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], optimizing
ms.assetid: 29ff985d-9bf5-4678-b62d-aad12def75fb
ms.openlocfilehash: 354ec1678747be57d387673f2611d526df8dfb47
ms.sourcegitcommit: 0ad35b26e405bbde17dc0bd0141e72f78f0a38fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/18/2019
ms.locfileid: "67194729"
---
# <a name="optimizing-control-drawing"></a>Denetim Çizimini İyileştirme

Denetim kendisini bir kapsayıcı tarafından sağlanan cihaz bağlamına çizmek için istendiğinde, genellikle cihaz bağlamına (örneğin, kalemler, fırçaları ve yazı tipleri) GDI nesneleri seçer, çizim işlemlerini gerçekleştirir ve önceki GDI nesnelerini geri yükler. Denetimleri daha önce seçilen nesneleri ayrı ayrı geri yüklemezseniz aynı cihaz bağlamına çizilecek olan birden çok denetim kapsayıcısı içerir ve her denetim gerektiren GDI nesneleri seçer, zaman kaydedilebilir. Tüm denetimleri çizilmiş sonra kapsayıcı otomatik olarak özgün nesneleri geri yükleyebilirsiniz.

Bir kapsayıcı bu tekniği destekleyip desteklemediğini algılamak için bir denetim çağırabilirsiniz [COleControl::IsOptimizedDraw](../mfc/reference/colecontrol-class.md#isoptimizeddraw) üye işlevi. Bu işlev döndürürse **TRUE**, denetimin önceden seçilen nesneleri geri yüklemek için normal adımını atlayabilirsiniz.

Aşağıdaki (iyileştirilmemiş) içeren bir denetim göz önünde bulundurun `OnDraw` işlevi:

[!code-cpp[NVC_MFC_AxOpt#15](../mfc/codesnippet/cpp/optimizing-control-drawing_1.cpp)]

Bu örnekte fırça ve Kalem kendi yıkıcıları çağrılacaktır, bunlar kapsam dışına çıkmadan, yani, yerel değişkenler olan (zaman `OnDraw` işlev sona erer). Yıkıcılar, karşılık gelen GDI nesneleri silin dener. Ancak bunları döndürme bağlı cihaz bağlamına seçili bırakın planlıyorsanız, bunlar silinmemelidir `OnDraw`.

Önlemek için [CPen](../mfc/reference/cpen-class.md) ve [CBrush](../mfc/reference/cbrush-class.md) zaman yok ediliyor nesnelerin `OnDraw` tamamlandığında, üye değişkenlerine yerel değişkenler yerine bunları depolayın. Denetimin sınıf bildiriminde bildirimleri için iki yeni üye değişkenleri ekleyin:

[!code-cpp[NVC_MFC_AxOpt#16](../mfc/codesnippet/cpp/optimizing-control-drawing_2.h)]
[!code-cpp[NVC_MFC_AxOpt#17](../mfc/codesnippet/cpp/optimizing-control-drawing_3.h)]

Ardından, `OnDraw` işlevi yazılan gibi:

[!code-cpp[NVC_MFC_AxOpt#18](../mfc/codesnippet/cpp/optimizing-control-drawing_4.cpp)]

Bu yaklaşım her seferinde oluşturma fırça ve Kalem önler `OnDraw` çağrılır. Hızlı geliştirme, ek örneği veri sürdürme karşılığında sunulur.

ForeColor ya da BackColor özelliği değişirse, kalem veya fırça yeniden oluşturulması gerekir. Bunu yapmak için geçersiz kılma [OnForeColorChanged](../mfc/reference/colecontrol-class.md#onforecolorchanged) ve [OnBackColorChanged](../mfc/reference/colecontrol-class.md#onbackcolorchanged) üye işlevler:

[!code-cpp[NVC_MFC_AxOpt#19](../mfc/codesnippet/cpp/optimizing-control-drawing_5.cpp)]

Son olarak, gereksiz ortadan kaldırmak için `SelectObject` çağrıları değiştirme `OnDraw` gibi:

[!code-cpp[NVC_MFC_AxOpt#20](../mfc/codesnippet/cpp/optimizing-control-drawing_6.cpp)]

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX Denetimleri: İyileştirme](../mfc/mfc-activex-controls-optimization.md)<br/>
[COleControl Sınıfı](../mfc/reference/colecontrol-class.md)<br/>
[MFC ActiveX Denetimleri](../mfc/mfc-activex-controls.md)<br/>
[MFC ActiveX Denetim Sihirbazı](../mfc/reference/mfc-activex-control-wizard.md)<br/>
[MFC ActiveX Denetimleri: ActiveX Denetimi Boyama](../mfc/mfc-activex-controls-painting-an-activex-control.md)
