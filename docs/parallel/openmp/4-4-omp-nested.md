---
title: 4.4 OMP_NESTED | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-parallel
ms.topic: conceptual
dev_langs:
- C++
ms.assetid: fd17b6f4-84e8-44c0-a96a-3a9e5ba33688
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1779b75774a2177a0d6a4f0661406e28b479a7ee
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690276"
---
# <a name="44-ompnested"></a>4.4 OMP_NESTED
`OMP_NESTED` Ortam değişkeni etkinleştirir veya iç içe geçmiş paralellik etkin veya çağırarak devre dışı sürece iç içe geçmiş paralellik devre dışı bırakır `o` **mp_set_nested** kitaplığı yordamı. Varsa kümesine **TRUE**, iç içe geçmiş paralellik etkindir; bu ayarlanmışsa **yanlış**, iç içe geçmiş paralellik devre dışıdır. Varsayılan değer **FALSE**.  
  
 Örnek:  
  
```  
setenv OMP_NESTED TRUE  
```  
  
## <a name="cross-reference"></a>Çapraz referans:  
  
-   `omp_set_nested` işlev, bkz: [bölüm 3.1.9](../../parallel/openmp/3-1-9-omp-set-nested-function.md) sayfasında 40.