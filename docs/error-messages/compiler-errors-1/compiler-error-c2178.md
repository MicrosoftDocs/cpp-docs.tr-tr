---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2178'
title: Derleyici hatası C2178
ms.date: 05/08/2017
f1_keywords:
- C2178
helpviewer_keywords:
- C2178
ms.assetid: 79a14158-17f3-4221-bd06-9d675c49cef4
ms.openlocfilehash: 7a93293fdb87f30827b8b9c3c6d38066b0c76798
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322168"
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
