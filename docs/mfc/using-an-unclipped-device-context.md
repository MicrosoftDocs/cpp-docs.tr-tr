---
description: 'Hakkında daha fazla bilgi edinin: kırpılmamış cihaz bağlamı kullanma'
title: Kesilmemiş Bir Cihaz Bağlamı Kullanma
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], unclipped device context
ms.assetid: 9c020063-73da-4803-bf7b-2e1fd950c9ed
ms.openlocfilehash: 76131d35b108b04caf0b07be8c46e250120f9f62
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202645"
---
# <a name="using-an-unclipped-device-context"></a>Kesilmemiş Bir Cihaz Bağlamı Kullanma

Denetiminizin istemci dikdörtgeni dışında boyamadığından kesinlikle emin değilseniz, tarafından yapılan çağrıyı devre dışı bırakarak küçük ancak algılanabilir bir hızlı kazanç elde edebilirsiniz `IntersectClipRect` `COleControl` . Bunu yapmak için [Coelcontrol:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags)tarafından döndürülen bayraklar kümesinden *clipPaintDC* bayrağını kaldırın. Örneğin:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/using-an-unclipped-device-context_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#14](../mfc/codesnippet/cpp/using-an-unclipped-device-context_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/using-an-unclipped-device-context_3.cpp)]

Bu bayrağı kaldırma kodu, MFC ActiveX Denetim Sihirbazı ile denetiminizi oluştururken [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfasında **kırpılmamış cihaz bağlamı** seçeneğini belirlerseniz otomatik olarak üretilir.

Penceresiz etkinleştirme kullanıyorsanız, bu iyileştirmenin hiçbir etkisi yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri: Iyileştirme](../mfc/mfc-activex-controls-optimization.md)
