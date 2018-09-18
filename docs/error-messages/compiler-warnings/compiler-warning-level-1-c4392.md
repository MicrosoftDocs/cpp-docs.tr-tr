---
title: Derleyici Uyarısı (düzey 1) C4392 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4392
dev_langs:
- C++
helpviewer_keywords:
- C4392
ms.assetid: 817806ad-06a6-4b9e-8355-e25687c782dc
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 8632b91710668c44a75a4ba098c5da3790ba828f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46073829"
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