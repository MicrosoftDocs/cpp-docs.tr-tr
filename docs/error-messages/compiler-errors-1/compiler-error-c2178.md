---
title: Derleyici hatası C2178
ms.date: 05/08/2017
f1_keywords:
- C2178
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
ms.openlocfilehash: 85cac4919c048c30a3ed1ff5573a3c14b77da0bd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737198"
---
# <a name="compiler-error-c2178"></a>Derleyici hatası C2178

'*tanımlayıcı*' '*belirtici*' belirticisi ile bildirilemez

Bir bildirimde `mutable` belirleyicisi kullanıldı, ancak tanımlayıcıya bu bağlamda izin verilmiyor.

`mutable` belirleyicisi yalnızca sınıf veri üyelerinin adlarına uygulanabilir ve `const` veya `static`olarak belirtilen adlara uygulanamaz ve başvuru üyelerine uygulanamaz.

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
