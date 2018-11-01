---
title: Derleyici Hatası C2646
ms.date: 11/04/2016
f1_keywords:
- C2646
helpviewer_keywords:
- C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
ms.openlocfilehash: c02d7216df42681ae2ec733ae932d22861c1f0ee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572019"
---
# <a name="compiler-error-c2646"></a>Derleyici Hatası C2646

bir anonim struct veya union genel veya ad alanı kapsamında statik olarak bildirilmelidir

Bir anonim yapıda veya birleşimde genel yok veya ad alanı kapsamına ancak değil bildirilen `static`.

Aşağıdaki örnek, C2646 oluşturur ve bu sorunun nasıl gösterir:

```
// C2646.cpp
// compile with: /c
union { int i; };   // C2646 not static

// OK
static union { int j; };
union U { int i; };
```