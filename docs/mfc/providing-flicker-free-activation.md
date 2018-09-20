---
title: Titreşimsiz etkinleştirme sağlama | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- MFC ActiveX controls [MFC], flicker-free
- flicker, MFC ActiveX controls
- activation [MFC], flicker-free
ms.assetid: bcb24b77-31d8-44a0-8c58-2ea6213b4c43
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: bd9f780472b8256f6d8332ecbde08138d85c8ebd
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46378333"
---
# <a name="providing-flicker-free-activation"></a>Titreşimsiz Etkinleştirme Sağlama

Denetim kendisini etkin ve etkin durumda aynı şekilde çizer (ve penceresiz etkinleştirme kullanmaz varsa), çizim işlemlerini ve normalde devre dışı arasında geçiş yaparken ortaya eşlik eden görsel titreşimini ortadan kaldırabilir ve etkin durumları. Bunu yapmak için dahil **noFlickerActivate** bayrağı tarafından döndürülen bayrakları kümesini [COleControl::GetControlFlags](../mfc/reference/colecontrol-class.md#getcontrolflags). Örneğin:

[!code-cpp[NVC_MFC_AxOpt#5](../mfc/codesnippet/cpp/providing-flicker-free-activation_1.cpp)]
[!code-cpp[NVC_MFC_AxOpt#13](../mfc/codesnippet/cpp/providing-flicker-free-activation_2.cpp)]
[!code-cpp[NVC_MFC_AxOpt#7](../mfc/codesnippet/cpp/providing-flicker-free-activation_3.cpp)]

Seçerseniz bu bayrak eklenecek kodu otomatik olarak oluşturulan **titreşimsiz etkinleştirme** seçeneğini [denetim ayarları](../mfc/reference/control-settings-mfc-activex-control-wizard.md) denetiminiz MFC ActiveX Denetim Sihirbazı ile oluştururken sayfasında.

Penceresiz etkinleştirme kullanıyorsanız, bu en iyi duruma getirme bir etkisi yoktur.

## <a name="see-also"></a>Ayrıca Bkz.

[MFC ActiveX Denetimleri: İyileştirme](../mfc/mfc-activex-controls-optimization.md)

