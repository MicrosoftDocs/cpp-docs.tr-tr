---
title: Derleyici hatası C3076
ms.date: 11/04/2016
f1_keywords:
- C3076
helpviewer_keywords:
- C3076
ms.assetid: 8a87b3e4-2c17-4b87-9622-ef0962d6a34e
ms.openlocfilehash: f3ce849113b0fc21a192f748bc46fc35be48880d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749639"
---
# <a name="compiler-error-c3076"></a>Derleyici hatası C3076

' örnek ': bir başvuru türünün örneğini (' Type ') yerel bir türde katıştıramazsınız

Yerel tür bir CLR türü örneği içeremez.

Daha fazla bilgi için bkz [ C++ . başvuru türleri için yığın semantiği](../../dotnet/cpp-stack-semantics-for-reference-types.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3076 oluşturur.

```cpp
// C3076.cpp
// compile with: /clr /c
ref struct U {};

struct V {
   U y;   // C3076
};

ref struct W {
   U y;   // OK
};
```
