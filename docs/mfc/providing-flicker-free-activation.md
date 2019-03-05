---
title: Titreşimsiz Etkinleştirme Sağlama
ms.date: 11/04/2016
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
ms.openlocfilehash: fad24d6201260e87ff32436752a9fbf035e822ae
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57287680"
---
# <a name="providing-flicker-free-activation"></a>Titreşimsiz Etkinleştirme Sağlama

Denetim kendisini etkin ve etkin durumda aynı şekilde çizer (ve penceresiz etkinleştirme kullanmaz varsa), çizim işlemlerini ve normalde devre dışı arasında geçiş yaparken ortaya eşlik eden görsel titreşimini ortadan kaldırabilir ve etkin durumları. Bunu yapmak için dahil **noFlickerActivate** bayrağı tarafından döndürülen bayrakları kümesini [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Örneğin:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]

Seçerseniz bu bayrak eklenecek kodu otomatik olarak oluşturulan **titreşimsiz etkinleştirme** seçeneğini [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) denetiminiz MFC ActiveX Denetim Sihirbazı ile oluştururken sayfasında.

Penceresiz etkinleştirme kullanıyorsanız, bu en iyi duruma getirme bir etkisi yoktur.

## <a name="see-also"></a>Ayrıca bkz.

[MFC ActiveX denetimleri: En iyi duruma getirme](../mfc/mfc-activex-controls-optimization.md)
