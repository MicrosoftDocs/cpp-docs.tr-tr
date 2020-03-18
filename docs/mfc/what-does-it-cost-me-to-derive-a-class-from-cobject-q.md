---
title: CObject'ten Sınıf Türetmenin Bana Maliyeti Nedir?
ms.date: 11/04/2016
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
ms.openlocfilehash: 8f83bf9ee522487761aaa865a8315a174a47302d
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446048"
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>CObject'ten Sınıf Türetmenin Bana Maliyeti Nedir?

[CObject](../mfc/reference/cobject-class.md) sınıfından türetmede ek yük düşüktür. Türetilmiş sınıfınız yalnızca dört sanal işlevi ve tek bir [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) nesnesini devralır.

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı: Sık Sorulan Sorular](../mfc/cobject-class-frequently-asked-questions.md)
