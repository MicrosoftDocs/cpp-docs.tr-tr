---
title: "3.1.10 omp_get_nested işlevi | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 48736a25-5c6e-4e2d-aad0-421087663a3c
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 36b213ee45018e7cc0ccf3a1cb99dcbd640d4457
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="3110-ompgetnested-function"></a>3.1.10 omp_get_nested İşlevi
`omp_get_nested` İşlevi, iç içe geçmiş paralellik etkinse, sıfır olmayan bir değer ve 0, devre dışı bırakılırsa döndürür. İç içe geçmiş paralellik hakkında daha fazla bilgi için sayfa 40 3.1.9 bölümüne bakın. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 Bir uygulama iç içe geçmiş paralellik uygulamadığında bu işlevi her zaman 0 değerini döndürür.