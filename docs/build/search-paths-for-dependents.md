---
title: Bağımlılıklar için yollar Ara | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NMAKE program, dependents
- dependents, NMAKE
ms.assetid: bf998e47-da74-48b5-891d-d3d8ce57264b
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 577fc7e44bfff35cf7efdcff20dc4cdca1c7001e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
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