---
title: Kesilmemiş bir cihaz bağlamı kullanma | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 479009865fe9fd226466059382456f403e90c18a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46389596"
---
# <a name="using-an-unclipped-device-context"></a>Kesilmemiş Bir Cihaz Bağlamı Kullanma

Denetiminiz dışında istemci dikdörtgeni boyama değil kesinlikle emin olduğunuzda çağrısı devre dışı bırakarak küçük ancak algılanabilir hızı kazanç sağlarsınız `IntersectClipRect` tarafından yapılan `COleControl`. Bunu yapmak için kaldırmak *clipPaintDC* bayrağı tarafından döndürülen bayrakları kümesinden [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Örneğin:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]

Seçerseniz bu bayrağı kaldırmak için kodu otomatik olarak oluşturulan **kesilmemiş cihaz bağlamı** seçeneğini [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfasında, MFC ActiveX Denetim Sihirbazı ile denetiminizi oluştururken.

Penceresiz etkinleştirme kullanıyorsanız, bu en iyi duruma getirme bir etkisi yoktur.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri: İyileştirme](../mfc/mfc-activex-controls-optimization.md)

