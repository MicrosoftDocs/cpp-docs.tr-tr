---
title: CObject'ten Yeni Sınıflar Türetmem Gerekiyor mu?
ms.date: 11/04/2016
f1_keywords:
- CObject
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
ms.openlocfilehash: 30eb3ce5bbb72ab685ed891644a478a36026ebea
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62352391"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject'ten Yeni Sınıflar Türetmem Gerekiyor mu?

Hayır, gerekmez.

Öğesinden bir sınıf türetin [CObject](../mfc/reference/cobject-class.md) sağladığı, serileştirme veya dinamik creatability gibi özellikleri gerektiğinde. Birçok veri sınıfları aktarımlar için iyi bir fikir genellikle, bu nedenle, dosyaya seri hale gerek `CObject`. Türetilen bir sınıf örneği için `CObject`, bkz: [Scribble örneğinin](../overview/visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca bkz.

[CObject Sınıfı: Sık Sorulan Sorular](../mfc/cobject-class-frequently-asked-questions.md)
