---
description: "Hakkında daha fazla bilgi edinin: CObject 'ten Yeni Sınıflar Türetmem gerekiyor mu?"
title: CObject'ten Yeni Sınıflar Türetmem Gerekiyor mu?
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: d37570cb62f1ee274e4cea85fc95a9221c95fd8a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261313"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject'ten Yeni Sınıflar Türetmem Gerekiyor mu?

Hayır, hayır.

Serileştirme veya dinamik uyumluluk gibi, sağladığı tesislere ihtiyacınız olduğunda [CObject](reference/cobject-class.md) 'ten bir sınıf türetirsiniz. Birçok veri sınıfının dosyalara serileştirilmesi gerekir, bu nedenle çoğu zaman bunları öğesinden türetmek iyi bir fikirdir `CObject` . Öğesinden türetilen bir sınıf örneği için `CObject` bkz. [karalama örneği](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[CObject sınıfı: sık sorulan sorular](cobject-class-frequently-asked-questions.md)
