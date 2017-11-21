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
ms.openlocfilehash: cf777c89c78ab844b61138c30a5a9a25ca6b91d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
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