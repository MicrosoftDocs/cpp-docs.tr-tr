---
title: initonly (C++/CLI)
ms.date: 11/04/2016
f1_keywords:
- initonly_cpp
- initonly
helpviewer_keywords:
- initonly attribute [C++]
ms.assetid: f745d7fa-dc08-46f1-9b97-0977be58a008
ms.openlocfilehash: 970800968733a285929c3bfa42594360203e573a
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74988476"
---
# <a name="initonly-ccli"></a>initonly (C++/CLI)

**initonly** , değişken atamasının yalnızca bildirimin parçası olarak veya aynı sınıftaki bir statik oluşturucuda gerçekleşebileceğini belirten bağlama duyarlı bir anahtar sözcüktür.

Aşağıdaki örnek `initionly`nasıl kullanacağınızı gösterir:

```cpp
// mcpp_initonly.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int staticConst1;

   initonly
   static int staticConst2 = 0;

   static Y1() {
      staticConst1 = 0;
   }
};
```

## <a name="see-also"></a>Ayrıca bkz.

[Sınıflar ve Yapılar](../extensions/classes-and-structs-cpp-component-extensions.md)
