---
title: "Koşullu derleme belirtme A.2 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: de4a21b9-f987-4738-9f13-c4795f6f2dff
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b0888a8bfc3d920ed3338b2ab6182c09cb75097a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="a2---specifying-conditional-compilation"></a>A.2   Koşullu Derlemeyi Belirtme
Aşağıdaki örnekler OpenMP makrosu kullanarak koşullu derleme kullanımını göstermek `_OPENMP` ([bölüm 2.2](../../parallel/openmp/2-2-conditional-compilation.md) sayfasında 8). OpenMP derleme ile `_OPENMP` hale makrosu tanımlı.  
  
```  
# ifdef _OPENMP   
    printf_s("Compiled by an OpenMP-compliant implementation.\n");  
# endif  
```  
  
 Tanımlanan önişlemci işleci tek bir yönergeye sınanacak birden fazla makrosu sağlar.  
  
```  
# if defined(_OPENMP) && defined(VERBOSE)  
    printf_s("Compiled by an OpenMP-compliant implementation.\n");  
# endif  
```