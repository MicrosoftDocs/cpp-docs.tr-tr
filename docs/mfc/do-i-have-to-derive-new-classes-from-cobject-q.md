---
title: CObject'ten Yeni Sınıflar Türetmem Gerekiyor mu?
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: 371ede0f0921182c066b4cb224e66b18eb6f1208
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84616733"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject'ten Yeni Sınıflar Türetmem Gerekiyor mu?

Hayır, hayır.

Serileştirme veya dinamik uyumluluk gibi, sağladığı tesislere ihtiyacınız olduğunda [CObject](reference/cobject-class.md) 'ten bir sınıf türetirsiniz. Birçok veri sınıfının dosyalara serileştirilmesi gerekir, bu nedenle çoğu zaman bunları öğesinden türetmek iyi bir fikirdir `CObject` . Öğesinden türetilen bir sınıf örneği için `CObject` bkz. [karalama örneği](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı: Sıkça Sorulan Sorular](cobject-class-frequently-asked-questions.md)
