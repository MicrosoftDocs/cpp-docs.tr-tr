---
title: Derleyici hatası C2178
ms.date: 05/08/2017
f1_keywords:
- C2178
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
ms.openlocfilehash: 4904c7009151748b4585060c816e0bd5c407be33
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225559"
---
# <a name="compiler-error-c2178"></a>Derleyici hatası C2178

'*tanımlayıcı*' '*belirtici*' belirticisi ile bildirilemez

Bir **`mutable`** bildirimde tanımlayıcı kullanıldı, ancak tanımlayıcıya bu bağlamda izin verilmiyor.

**`mutable`** Tanımlayıcı yalnızca sınıf veri üyelerinin adlarına uygulanabilir, veya tarafından belirtilen adlara uygulanamaz **`const`** **`static`** ve başvuru üyelerine uygulanamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2178 nasıl gerçekleşebileceğini ve nasıl düzeltileceğini gösterir.

```cpp
// C2178.cpp
// compile with: cl /c /W4 C2178.cpp

class S {
    mutable const int i; // C2178
    // To fix, declare either const or mutable, not both.
};

mutable int x = 4; // C2178
// To fix, remove mutable keyword
```
