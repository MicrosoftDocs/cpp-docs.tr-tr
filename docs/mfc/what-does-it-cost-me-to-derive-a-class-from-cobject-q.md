---
title: CObject'ten Sınıf Türetmenin Bana Maliyeti Nedir? | Microsoft Docs
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
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3ffff35cdef6cf2f730687334bbb56bc078371a7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/04/2018
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>CObject'ten Sınıf Türetmenin Bana Maliyeti Nedir?
Sınıfından türetilen içinde ek yükü [CObject](../mfc/reference/cobject-class.md) en alt düzeydedir. Yalnızca dört sanal işlevler ve tek bir türetilmiş sınıf devralır [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject Sınıfı: Sık Sorulan Sorular](../mfc/cobject-class-frequently-asked-questions.md)
