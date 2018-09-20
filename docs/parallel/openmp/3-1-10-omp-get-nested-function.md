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
ms.openlocfilehash: d019dd757080bbc87ff7aaab1a8745b2a3156b39
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392287"
---
# <a name="3110-ompgetnested-function"></a>3.1.10 omp_get_nested İşlevi

`omp_get_nested` İşlevi, iç içe geçmiş paralellik etkinse, sıfır dışında bir değeri ile 0 değilse döndürür. İç içe geçmiş paralellik hakkında daha fazla bilgi için bölümüne 3.1.9 40 sayfasında bakın. Biçimi aşağıdaki gibidir:

```
#include <omp.h>
int omp_get_nested(void);
```

Bir uygulama, iç içe geçmiş paralellik uygulamıyor, bu işlev her zaman 0 döndürür.