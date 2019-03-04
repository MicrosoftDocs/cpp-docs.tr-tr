---
title: Kesilmemiş Bir Cihaz Bağlamı Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
ms.openlocfilehash: 0f129c0bfa5bd76df4ba34b117e7ed8aa08c2ecb
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57270676"
---
# <a name="using-an-unclipped-device-context"></a>Kesilmemiş Bir Cihaz Bağlamı Kullanma

Denetiminiz dışında istemci dikdörtgeni boyama değil kesinlikle emin olduğunuzda çağrısı devre dışı bırakarak küçük ancak algılanabilir hızı kazanç sağlarsınız `IntersectClipRect` tarafından yapılan `COleControl`. Bunu yapmak için kaldırmak *clipPaintDC* bayrağı tarafından döndürülen bayrakları kümesinden [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Örneğin:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]

Seçerseniz bu bayrağı kaldırmak için kodu otomatik olarak oluşturulan **kesilmemiş cihaz bağlamı** seçeneğini [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfasında, MFC ActiveX Denetim Sihirbazı ile denetiminizi oluştururken.

Penceresiz etkinleştirme kullanıyorsanız, bu en iyi duruma getirme bir etkisi yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri: En iyi duruma getirme](../mfc/mfc-activex-controls-optimization.md)
