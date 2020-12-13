---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4392'
title: Derleyici Uyarısı (düzey 1) C4392
ms.date: 11/04/2016
f1_keywords:
- C4392
helpviewer_keywords:
- C4392
ms.assetid: 817806ad-06a6-4b9e-8355-e25687c782dc
ms.openlocfilehash: d10b966f6727ec3461255d3789a6e9a7aed78c22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97339897"
---
# <a name="compiler-warning-level-1-c4392"></a>Derleyici Uyarısı (düzey 1) C4392

' Signature ': iç işlev için yanlış sayıda bağımsız değişken, beklenen ' number ' bağımsız değişkeni

Bir derleyici iç öğesinin işlev bildiriminde yanlış sayıda bağımsız değişken vardı. Elde edilen görüntü doğru çalışmayabilir.

Bu uyarıyı düzeltmek için, bildirimi düzeltin ya da bildirimi silin ve yalnızca uygun üstbilgi dosyasını #include.

Aşağıdaki örnek C4392 oluşturur:

```cpp
// C4392.cpp
// compile with: /W1
// processor: x86
// uncomment the following line and delete the line that
// generated the warning to resolve
// #include "xmmintrin.h"

#ifdef  __cplusplus
extern "C" {
#endif

extern void _mm_stream_pd(double *dp);   // C4392

#ifdef  __cplusplus
}
#endif

int main()
{
}
```
