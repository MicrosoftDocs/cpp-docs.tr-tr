---
title: Kaydırıcı Denetim Stilleri
ms.date: 11/04/2016
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
ms.openlocfilehash: c6765445552826b71cca278c1fbbc66e500cb75a
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57296861"
---
# <a name="slider-control-styles"></a>Kaydırıcı Denetim Stilleri

Kaydırıcı denetimleri ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) dikey veya yatay hizalama olabilir. Değer çizgilerinin iki tarafında olabilir hem yüz veya hiçbiridir. Art arda değer aralığını belirtmek için de kullanılabilir. Bu özellikler, kaydırıcı denetimi oluşturduğunuzda, belirttiğiniz kaydırıcı denetim stilleri kullanarak denetlenir.

TBS_HORZ ve TBS_VERT stilleri kaydırıcı denetiminin yönünü belirleyin. Kaydırıcı denetimi yatay yönlendirme belirtmezseniz, yönlendirilmiş demektir.

TBS_AUTOTICKS stili değer aralığındaki her artış için onay işareti olan bir kaydırıcı denetimi oluşturur. Bu değer çizgilerinin çağırdığınızda otomatik olarak eklenen [SetRange](../mfc/reference/csliderctrl-class.md#setrange) üye işlevi. TBS_AUTOTICKS belirtmezseniz, üye işlevleri gibi kullanabileceğiniz [SetTic](../mfc/reference/csliderctrl-class.md#settic) ve [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq)çizgilerinin konumlarını belirtmek için. Değer çizgilerinin görüntülemez bir kaydırıcı denetimi oluşturmak için TBS_NOTICKS stilini kullanabilirsiniz.

Değer çizgilerinin kaydırıcı denetimi veya her iki tarafta da görüntüleyebilirsiniz. Yatay kaydırıcı denetimleri için TBS_BOTTOM veya TBS_TOP stili belirtebilirsiniz. Dikey kaydırıcı denetimleri için TBS_RIGHT veya TBS_LEFT stili belirtebilirsiniz. (Varsayılan ayarlar TBS_BOTTOM ve TBS_RIGHT gösterir.) Çizginiz için herhangi bir yönde kaydırıcı denetimi iki tarafındaki TBS_BOTH stilini belirtin.

Bir kaydırıcı denetimi, yalnızca oluşturduğunuzda TBS_ENABLESELRANGE stili belirtirseniz, bir seçim aralığını görüntüleyebilirsiniz. Bir kaydırıcı denetimi bu stilde, değer çizgilerinin seçimi aralığının başlangıç ve bitiş konumlarda (yerine, dikey çizgi) üçgenler olarak görüntülenir ve seçenek aralığındaki vurgulanır. Örneğin, seçim aralıkları basit bir zamanlama uygulama yararlı olabilir. Kullanıcı bir zamanlanan toplantı saati tanımlamak için bir gündeki saat karşılık gelen değer çizgileri aralığı seçebilirsiniz.

Varsayılan olarak, bir kaydırıcı denetiminin kaydırıcı uzunluğunu seçimi aralığı değişiklikleri olarak değişir. Kaydırıcı denetimi TBS_FIXEDLENGTH stili varsa, kaydırıcıyı uzunluğunu seçenek aralığındaki değişse bile aynı kalır. Bir kaydırıcı TBS_NOTHUMB stilde bir kaydırıcı denetimi içermez.

## <a name="see-also"></a>Ayrıca bkz.

[CSliderCtrl Kullanma](../mfc/using-csliderctrl.md)<br/>
[Denetimler](../mfc/controls-mfc.md)
