---
description: 'Daha fazla bilgi edinin: Flicker-Free etkinleştirme sağlama'
title: Titreşimsiz Etkinleştirme Sağlama
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
ms.openlocfilehash: c0af1ccdd4795f55296ff38e0e74bc6492f79eb1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248833"
---
# <a name="providing-flicker-free-activation"></a>Titreşimsiz Etkinleştirme Sağlama

Denetiminiz, etkin olmayan ve etkin durumlarında kendisini aynı şekilde çizirse (ve penceresiz etkinleştirme kullanmıyorsa), çizim işlemlerini ve normalde, etkin olmayan ve etkin durumlar arasında geçiş yaparken ortaya çıkan görsel titreşimi ortadan kaldırabilirsiniz. Bunu yapmak için [Coelcontrol:: GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags)tarafından döndürülen Flags kümesine **noFlickerActivate** bayrağını ekleyin. Örneğin:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]

Bu bayrağı dahil etmek için olan kod, MFC ActiveX Denetim Sihirbazı ile denetiminizi oluştururken [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) sayfasında **titreşimsiz etkinleştirme** seçeneğini belirlerseniz otomatik olarak üretilir.

Penceresiz etkinleştirme kullanıyorsanız, bu iyileştirmenin hiçbir etkisi yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri: Iyileştirme](../mfc/mfc-activex-controls-optimization.md)
