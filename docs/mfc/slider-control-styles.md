---
title: "Kaydırıcı denetim stilleri | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- slider controls [MFC], styles
- CSliderCtrl class [MFC], styles
- styles [MFC], CSliderCtrl
- styles [MFC], slider controls
ms.assetid: 64c491fc-5af1-4f97-ae30-854071b3dc02
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 747f5d55821c6911e80087ebbad65b2169e6fc49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="slider-control-styles"></a>Kaydırıcı Denetim Stilleri
Kaydırıcı denetimleri ([CSliderCtrl](../mfc/reference/csliderctrl-class.md)) dikey veya yatay yönlendirme olabilir. Değer çizgilerinin iki tarafında olabilir hem kenara veya hiçbiridir. Ardışık değerlerin aralığını belirtmek için de kullanılabilir. Bu özellikler, kaydırıcı denetimi oluşturduğunuzda, belirttiğiniz kaydırıcı denetim stilleri kullanılarak denetlenir.  
  
 `TBS_HORZ` Ve `TBS_VERT` stilleri kaydırıcı denetimi yönünü belirler. Kaydırıcı denetimi yatay yön belirtmezseniz, yönlendirilmiş demektir.  
  
 `TBS_AUTOTICKS` Stil çizgisi her artış için değerler aralığında olan kaydırıcı denetimi oluşturur. Bu değer çizgilerinin çağırdığınızda otomatik olarak eklenen [SetRange](../mfc/reference/csliderctrl-class.md#setrange) üye işlevi. Belirtmezseniz, `TBS_AUTOTICKS`, üye işlevleri gibi kullanabilir [SetTic](../mfc/reference/csliderctrl-class.md#settic) ve [SetTicFreq](../mfc/reference/csliderctrl-class.md#setticfreq)çizgilerinin konumlarını belirtmek için. Değer çizgilerinin görüntülemez kaydırıcı denetimi oluşturmak için kullanabileceğiniz `TBS_NOTICKS` stili.  
  
 Kaydırıcı denetimi biri veya her iki tarafta çizgilerinin görüntüleyebilirsiniz. Yatay kaydırıcı denetimleri için belirttiğiniz `TBS_BOTTOM` veya `TBS_TOP` stili. Dikey kaydırıcı denetimleri için belirttiğiniz `TBS_RIGHT` veya `TBS_LEFT` stili. (`TBS_BOTTOM` ve `TBS_RIGHT` varsayılan ayarları.) Kaydırıcı denetimi herhangi bir yönde her iki tarafında değer çizgileri için belirtmek `TBS_BOTH` stili.  
  
 Yalnızca belirttiğiniz kaydırıcı denetimi seçim aralığı görüntüleyebilirsiniz `TBS_ENABLESELRANGE` oluşturduğunuzda stili. Kaydırıcı denetimi bu stili olduğunda, bir seçim aralığının başlangıç ve bitiş konumlarda değer çizgilerinin üçgenler (yerine, dikey çizgi) olarak görüntülenir ve seçim aralığı vurgulanır. Örneğin, seçim aralıkları basit bir zamanlama uygulama yararlı olabilir. Kullanıcının zamanlanmış Toplantı zamanını tanımlamak için bir gündeki saat sayısıyla karşılık gelen değer çizgilerinin aralığını seçebilirsiniz.  
  
 Varsayılan olarak, kaydırıcıyı denetimin kaydırıcı uzunluğu seçimi aralığı değişiklikleri olarak değişir. Kaydırıcı denetimi varsa **TBS_FIXEDLENGTH** stili, kaydırıcıyı uzunluğu aynı kalır seçim aralığı değişse bile. Sahip kaydırıcı denetimi **TBS_NOTHUMB** stili kaydırıcıyı içermez.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CSliderCtrl kullanma](../mfc/using-csliderctrl.md)   
 [Denetimler](../mfc/controls-mfc.md)

