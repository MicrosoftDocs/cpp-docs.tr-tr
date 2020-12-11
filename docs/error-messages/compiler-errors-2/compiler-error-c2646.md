---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2646'
title: Derleyici hatası C2646
ms.date: 11/04/2016
f1_keywords:
- C2646
helpviewer_keywords:
- C2646
ms.assetid: 92ff1f02-5eaf-40a5-8b7a-a682f149e967
ms.openlocfilehash: 7aa378a0a2dbaeae78a63f97e83a84d94d861c72
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160824"
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
