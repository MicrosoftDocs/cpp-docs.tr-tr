---
title: Derleyici hatası C2646
ms.date: 11/04/2016
f1_keywords:
- C2646
helpviewer_keywords:
- C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
ms.openlocfilehash: a05c98564c4e45dc380690c1b8c9bace5fc14cf4
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87216160"
---
# <a name="compiler-error-c2646"></a>Derleyici hatası C2646

Genel veya ad alanı kapsamındaki anonim bir yapı veya birleşim statik olarak bildirilmelidir

Anonim bir yapıda veya birleşimde genel veya ad alanı kapsamı vardır ancak bildirilmemiş **`static`** .

Aşağıdaki örnek C2646 oluşturur ve nasıl düzeltileceğini gösterir:

```cpp
// C2646.cpp
// compile with: /c
union { int i; };   // C2646 not static

// OK
static union { int j; };
union U { int i; };
```
