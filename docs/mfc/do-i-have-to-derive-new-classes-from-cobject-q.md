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
ms.openlocfilehash: 51904ac06ae6c2db5586f8dc405f85145c5b1f30
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33343066"
---
# <a name="do-i-have-to-derive-new-classes-from-cobject"></a>CObject'ten Yeni Sınıflar Türetmem Gerekiyor mu?
Hayır, yok.  
  
 Öğesinden bir sınıf türetin [CObject](../mfc/reference/cobject-class.md) sağladığı seri hale getirme veya dinamik creatability gibi özellikleri gerektiğinde. Birçok veri sınıfları genellikle aktarımlar için iyi bir fikir nedenle dosyalara, seri hale gerek `CObject`. Türetilmiş bir sınıf örneği için `CObject`, bkz: [karalama örnek](../visual-cpp-samples.md).  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject Sınıfı: Sık Sorulan Sorular](../mfc/cobject-class-frequently-asked-questions.md)
