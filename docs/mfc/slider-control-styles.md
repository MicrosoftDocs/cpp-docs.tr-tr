---
title: Kaydırıcı denetim stilleri | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f76fbe9f85d978a5c2865b48720588b620508a07
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/26/2018
ms.locfileid: "36951058"
---
# <a name="slider-control-styles"></a>Kaydırıcı Denetim Stilleri
Kaydırıcı denetimleri ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) dikey veya yatay yönlendirme olabilir. Değer çizgilerinin iki tarafında olabilir hem kenara veya hiçbiridir. Ardışık değerlerin aralığını belirtmek için de kullanılabilir. Bu özellikler, kaydırıcı denetimi oluşturduğunuzda, belirttiğiniz kaydırıcı denetim stilleri kullanılarak denetlenir.  
  
 TBS_HORZ ve TBS_VERT stilleri kaydırıcı denetimi yönünü belirler. Kaydırıcı denetimi yatay yön belirtmezseniz, yönlendirilmiş demektir.  
  
 TBS_AUTOTICKS stil çizgisi her artış için değerler aralığında olan kaydırıcı denetimi oluşturur. Bu değer çizgilerinin çağırdığınızda otomatik olarak eklenen [SetRange](../mfc/reference/csliderctrl-class.md#setrange) üye işlevi. TBS_AUTOTICKS belirtmezseniz, üye işlevleri gibi kullanabilir [SetTic](../mfc/reference/csliderctrl-class.md#settic) ve [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq)çizgilerinin konumlarını belirtmek için. Değer çizgilerinin görüntülemez kaydırıcı denetimi oluşturmak için TBS_NOTICKS stili kullanabilirsiniz.  
  
 Kaydırıcı denetimi biri veya her iki tarafta çizgilerinin görüntüleyebilirsiniz. Yatay kaydırıcı denetimleri için TBS_BOTTOM veya TBS_TOP stili belirtebilirsiniz. Dikey kaydırıcı denetimleri için TBS_RIGHT veya TBS_LEFT stili belirtebilirsiniz. (TBS_BOTTOM ve TBS_RIGHT varsayılan ayarlarıdır.) Kaydırıcı denetimi herhangi bir yönde her iki tarafında değer çizgileri için TBS_BOTH stilini belirtin.  
  
 Kaydırıcı denetimi oluşturduğunuzda yalnızca TBS_ENABLESELRANGE stili belirtirseniz, seçim aralığı görüntüleyebilirsiniz. Kaydırıcı denetimi bu stili olduğunda, bir seçim aralığının başlangıç ve bitiş konumlarda değer çizgilerinin üçgenler (yerine, dikey çizgi) olarak görüntülenir ve seçim aralığı vurgulanır. Örneğin, seçim aralıkları basit bir zamanlama uygulama yararlı olabilir. Kullanıcının zamanlanmış Toplantı zamanını tanımlamak için bir gündeki saat sayısıyla karşılık gelen değer çizgilerinin aralığını seçebilirsiniz.  
  
 Varsayılan olarak, kaydırıcıyı denetimin kaydırıcı uzunluğu seçimi aralığı değişiklikleri olarak değişir. Kaydırıcı denetimi TBS_FIXEDLENGTH stili varsa, kaydırıcıyı uzunluğu seçim aralığı değişse bile aynı kalır. TBS_NOTHUMB stili içeren bir kaydırıcı denetimi kaydırıcıyı içermez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSliderCtrl kullanma](../mfc/using-csliderctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

