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
ms.workload: cplusplus
ms.openlocfilehash: 103067b28990854fb6522c19f4349a9607d65bab
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
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