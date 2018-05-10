---
title: 3.1.8 omp_get_dynamic işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: c03e2daf-29c9-49e3-9b67-b980ad1ab195
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: af7755173ab884a40a5f8a41f432f265cc1e6c32
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
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