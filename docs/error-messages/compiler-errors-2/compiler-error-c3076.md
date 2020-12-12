---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3076'
title: Derleyici hatası C3076
ms.date: 11/04/2016
f1_keywords:
- C3076
helpviewer_keywords:
- C3076
ms.assetid: 8a87b3e4-2c17-4b87-9622-ef0962d6a34e
ms.openlocfilehash: 27fbfe27d2e8efb1abee611701fdbde8f0d3d09f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97320186"
---
# <a name="compiler-error-c3076"></a>Derleyici hatası C3076

' örnek ': bir başvuru türünün örneğini (' Type ') yerel bir türde katıştıramazsınız

Yerel tür bir CLR türü örneği içeremez.

Daha fazla bilgi için bkz. [başvuru türleri için C++ yığın semantiği](../../dotnet/cpp-stack-semantics-for-reference-types.md).

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
