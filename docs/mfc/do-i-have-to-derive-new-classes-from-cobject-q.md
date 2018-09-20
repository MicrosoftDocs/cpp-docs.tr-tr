---
title: CObject'ten Yeni Sınıflar Türetmem Gerekiyor mu? | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- derived classes [MFC], from CObject
- CObject class [MFC], when to use
ms.assetid: 26021031-feaf-424c-80d1-9547c4409d6a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ec080e556b57afadbc3d958f4dba5ac6393108aa
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46408914"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject'ten Yeni Sınıflar Türetmem Gerekiyor mu?

Hayır, gerekmez.

Öğesinden bir sınıf türetin [CObject](../mfc/reference/cobject-class.md) sağladığı, serileştirme veya dinamik creatability gibi özellikleri gerektiğinde. Birçok veri sınıfları aktarımlar için iyi bir fikir genellikle, bu nedenle, dosyaya seri hale gerek `CObject`. Türetilen bir sınıf örneği için `CObject`, bkz: [Scribble örneğinin](../visual-cpp-samples.md).

## <a name="see-also"></a>Ayrıca Bkz.

[CObject Sınıfı: Sık Sorulan Sorular](../mfc/cobject-class-frequently-asked-questions.md)
