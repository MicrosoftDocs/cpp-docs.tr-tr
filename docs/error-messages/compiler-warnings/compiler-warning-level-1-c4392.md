---
title: Derleyici Uyarısı (düzey 1) C4392
ms.date: 11/04/2016
f1_keywords:
- C4392
helpviewer_keywords:
- C4392
ms.assetid: 817806ad-06a6-4b9e-8355-e25687c782dc
ms.openlocfilehash: 1dc0c546509b17132358f432f6a781035a314a72
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386427"
---
# <a name="compiler-warning-level-1-c4392"></a>Derleyici Uyarısı (düzey 1) C4392

'imza': iç işlev için bağımsız değişkenler yanlış sayıda 'number' bağımsız değişkeni bekleniyordu

Bir işlev bildirimi bir iç derleyici için yanlış sayıda bağımsız değişken var. Elde edilen görüntü düzgün çalışmayabilir.

Bu uyarıyı düzeltmek için bildirimi düzeltin ya da silme bildirimi ve yalnızca # uygun üstbilgi dosyasını include.

Aşağıdaki örnek, C4392 oluşturur:

```
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