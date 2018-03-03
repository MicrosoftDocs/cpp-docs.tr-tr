---
title: "CObject'ten Sınıf Türetmenin Bana Maliyeti Nedir? | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CObject
dev_langs:
- C++
helpviewer_keywords:
- CObject class [MFC], overhead of derived classes [MFC]
ms.assetid: 9b92c98b-b3dd-48a7-9d24-c3b8554edf90
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 253982da087dfc4b8ae9878b9788529960ecd8a3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="what-does-it-cost-me-to-derive-a-class-from-cobject"></a>CObject'ten Sınıf Türetmenin Bana Maliyeti Nedir?
Sınıfından türetilen içinde ek yükü [CObject](../mfc/reference/cobject-class.md) en alt düzeydedir. Yalnızca dört sanal işlevler ve tek bir türetilmiş sınıf devralır [CRuntimeClass](../mfc/reference/cruntimeclass-structure.md) nesnesi.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [CObject Sınıfı: Sık Sorulan Sorular](../mfc/cobject-class-frequently-asked-questions.md)
