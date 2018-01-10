---
title: "Bağımlılıklar için yollar Ara | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f6093db4ac8e0c88dfe6e4b5a5463e5ee8d24349
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="search-paths-for-dependents"></a>Bağımlılıklar için Yollar Ara
Her bağlı şekilde belirtilen bir isteğe bağlı arama yolu vardır:  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
{directory[;directory...]}dependent  
```  
  
## <a name="remarks"></a>Açıklamalar  
 NMAKE bağımlı geçerli dizinin ilk olarak ve belirtilen sırada dizinlerde arar. Makro bölümünü veya tümünü bir arama yolu belirtebilirsiniz. Dizin adı kaşlı ({}); alın birden çok dizin, noktalı virgül (;) ayırın. Hiçbir boşluk ya da sekme izin verilir.  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Bağımlılıklar](../build/dependents.md)