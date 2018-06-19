---
title: 3.1.10 omp_get_nested işlevi | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7f447da6957cb385ace918120eb7ed7a5420e9f0
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686727"
---
# <a name="3110-ompgetnested-function"></a>3.1.10 omp_get_nested İşlevi
`omp_get_nested` İşlevi, iç içe geçmiş paralellik etkinse, sıfır olmayan bir değer ve 0, devre dışı bırakılırsa döndürür. İç içe geçmiş paralellik hakkında daha fazla bilgi için sayfa 40 3.1.9 bölümüne bakın. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 Bir uygulama iç içe geçmiş paralellik uygulamadığında bu işlevi her zaman 0 değerini döndürür.