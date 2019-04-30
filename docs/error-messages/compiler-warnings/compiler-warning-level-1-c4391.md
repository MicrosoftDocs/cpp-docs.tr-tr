---
title: Derleyici Uyarısı (düzey 1) C4391
ms.date: 11/04/2016
f1_keywords:
- C4391
helpviewer_keywords:
- C4391
ms.assetid: 95c6182c-fae9-4174-8f7b-98aa352e68ca
ms.openlocfilehash: d9d1cebe08a6a163d76271ab001ec91b7cee82a2
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386466"
---
# <a name="compiler-warning-level-1-c4391"></a>Derleyici Uyarısı (düzey 1) C4391

'imza': iç işlev için yanlış dönüş türü, 'type' bekleniyor

Bir işlev bildirimi için bir iç derleyici hatalı dönüş türüne sahip. Elde edilen görüntü düzgün çalışmayabilir.

Bu uyarıyı düzeltmek için bildirimi düzeltin ya da silme bildirimi ve yalnızca # uygun üstbilgi dosyasını include.

Aşağıdaki örnek, C4391 oluşturur:

```
// C4391.cpp
// compile with: /W1
// processor: x86
// uncomment the following line and delete the line that
// generated the warning to resolve
// #include "xmmintrin.h"

#ifdef  __cplusplus
extern "C" {
#endif

extern void _mm_load_ss(float *p);   // C4391

#ifdef  __cplusplus
}
#endif

int main()
{
}
```