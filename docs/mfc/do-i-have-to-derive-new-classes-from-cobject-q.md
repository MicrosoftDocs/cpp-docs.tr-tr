---
title: CObject'ten Yeni Sınıflar Türetmem Gerekiyor mu?
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: c2361967dcfce5e46aeec65ade3d7056b362949d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50636611"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject'ten Yeni Sınıflar Türetmem Gerekiyor mu?

Hayır, gerekmez.

Öğesinden bir sınıf türetin [CObject](../mfc/reference/cobject-class.md) sağladığı, serileştirme veya dinamik creatability gibi özellikleri gerektiğinde. Birçok veri sınıfları aktarımlar için iyi bir fikir genellikle, bu nedenle, dosyaya seri hale gerek `CObject`. Türetilen bir sınıf örneği için `CObject`, bkz: [Scribble örneğinin](../visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı: Sık Sorulan Sorular](../mfc/cobject-class-frequently-asked-questions.md)
