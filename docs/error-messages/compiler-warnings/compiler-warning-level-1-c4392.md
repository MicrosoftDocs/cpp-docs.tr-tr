---
title: Derleyici Uyarısı (düzey 1) C4392
ms.date: 11/04/2016
f1_keywords:
- C4392
helpviewer_keywords:
- C4392
ms.assetid: 817806ad-06a6-4b9e-8355-e25687c782dc
ms.openlocfilehash: b19080f4a86267a48618a5f40d7576c07c96c18a
ms.sourcegitcommit: e5192a25c084eda9eabfa37626f3274507e026b3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73966102"
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