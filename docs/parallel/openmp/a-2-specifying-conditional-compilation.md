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
ms.workload: cplusplus
ms.openlocfilehash: 93557eaae2c8661697f7bda383b50f2e1ba9e2cb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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