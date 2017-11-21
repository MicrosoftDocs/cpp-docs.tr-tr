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
ms.openlocfilehash: 0447fd872a44d2c1eefb751e501eba4df5ec8b8f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="3110-ompgetnested-function"></a>3.1.10 omp_get_nested İşlevi
`omp_get_nested` İşlevi, iç içe geçmiş paralellik etkinse, sıfır olmayan bir değer ve 0, devre dışı bırakılırsa döndürür. İç içe geçmiş paralellik hakkında daha fazla bilgi için sayfa 40 3.1.9 bölümüne bakın. Biçimi aşağıdaki gibidir:  
  
```  
#include <omp.h>  
int omp_get_nested(void);  
```  
  
 Bir uygulama iç içe geçmiş paralellik uygulamadığında bu işlevi her zaman 0 değerini döndürür.