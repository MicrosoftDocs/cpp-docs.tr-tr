---
title: CObject'ten Yeni Sınıflar Türetmem Gerekiyor mu?
ms.date: 11/04/2016
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: d38e589f371fc56f5566c56de7b19c366065a503
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446929"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject'ten Yeni Sınıflar Türetmem Gerekiyor mu?

Hayır, hayır.

Serileştirme veya dinamik uyumluluk gibi, sağladığı tesislere ihtiyacınız olduğunda [CObject](../mfc/reference/cobject-class.md) 'ten bir sınıf türetirsiniz. Birçok veri sınıfının dosyalara serileştirilmesi gerekir, bu nedenle çoğunlukla `CObject`türetmeniz iyi bir fikirdir. `CObject`türetilen bir sınıf örneği için bkz. [karalama örneği](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı: Sık Sorulan Sorular](../mfc/cobject-class-frequently-asked-questions.md)
