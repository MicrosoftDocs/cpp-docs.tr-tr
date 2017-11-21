---
title: "3.1.8 omp_get_dynamic işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 7507a5ef177ab3415b9cde41b250337cbed1cc6c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="318-ompgetdynamic-function"></a>3.1.8 omp_get_dynamic İşlevi
**Omp_get_dynamic** işlevi, iş parçacıklarının dinamik ayarlama etkinleştirilmişse ve 0 döndürür sıfır olmayan bir değer döndürür. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
int omp_get_dynamic(void);  
```  
  
 Uygulama iş parçacığı sayısını dinamik olarak ayarlamayı uygulamadığında bu işlev, her zaman 0 döndürür.  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   Dinamik iş parçacığı ayarlama açıklaması için bkz: [bölüm 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39.