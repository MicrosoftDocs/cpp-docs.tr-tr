---
title: 4.4 OMP_NESTED | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 50b2b110f191252702da9a2b6eed99baa40b7814
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED
`OMP_NESTED` Ortam değişkeni etkinleştirir veya iç içe geçmiş paralellik etkin veya çağırarak devre dışı sürece iç içe geçmiş paralellik devre dışı bırakır `o` **mp_set_nested** kitaplığı yordamı. Varsa kümesine **TRUE**, iç içe geçmiş paralellik etkindir; bu ayarlanmışsa **yanlış**, iç içe geçmiş paralellik devre dışıdır. Varsayılan değer **FALSE**.  
  
 Örnek:  
  
```  
setenv OMP_NESTED TRUE  
```  
  
## <a name="cross-reference"></a>Çapraz referans:  
  
-   `omp_set_nested`işlev, bkz: [bölüm 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) sayfasında 40.