---
title: 4.3 OMP_DYNAMIC | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a15edefb-1f85-4f06-a427-beb3cfc4434f
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2b23719d1559a00b807f724a3e31eb7b673a5a17
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="43-ompdynamic"></a>4.3 OMP_DYNAMIC
**Omp_dynamıc** ortam değişkeni etkinleştirir veya dinamik ayarlama açıkça etkin veya devre dışı çağıraraksüreceparalelbölgeleryürütmeiçinkullanılabilirişparçacığısayısınıdinamikolarakayarlamayıdevredışıbırakır**omp_set_dynamic** kitaplığı yordamı. Değeri olmalıdır **TRUE** veya **FALSE**.  
  
 Varsa kümesine **doğru**, paralel bölgeler yürütmek için kullanılan iş parçacıklarının en iyi sistem kaynaklarını kullanmak için çalışma zamanı ortamı tarafından ayarlanmış.  Varsa kümesine **yanlış**, dinamik ayarlama devre dışıdır. Varsayılan uygulama tanımlı bir durumdur.  
  
 Örnek:  
  
```  
setenv OMP_DYNAMIC TRUE  
```  
  
## <a name="cross-references"></a>Çapraz referanslar:  
  
-   Paralel bölgeler hakkında daha fazla bilgi için bkz: [bölüm 2.3](../../parallel/openmp/2-3-parallel-construct.md) sayfasında 8.  
  
-   **omp_set_dynamic** işlev, bkz: [bölüm 3.1.7](../../parallel/openmp/3-1-7-omp-set-dynamic-function.md) sayfasında 39.