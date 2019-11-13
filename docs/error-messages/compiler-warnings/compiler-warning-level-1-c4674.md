---
title: Derleyici Uyarısı (düzey 1) C4674
ms.date: 11/04/2016
f1_keywords:
- C4674
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
ms.openlocfilehash: b9428a593ff59cbdfa6d8eb369413a560b4a5ad2
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052540"
---
# <a name="compiler-warning-level-1-c4674"></a>Derleyici Uyarısı (düzey 1) C4674

' Method ', ' static ' olarak bildirilmelidir ve tam olarak bir parametreye sahip olmalıdır

Bir dönüştürme işlecinin imzası doğru değildi. Yöntem, Kullanıcı tanımlı bir dönüştürme olarak kabul edilmez. İşleçleri tanımlama hakkında daha fazla bilgi için bkz. [Kullanıcı tanımlı işleçler (C++/CLI)](../../dotnet/user-defined-operators-cpp-cli.md) ve [Kullanıcı tanımlı dönüştürmeler (C++/CLI)](../../dotnet/user-defined-conversions-cpp-cli.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C4674 oluşturur.

```cpp
// C4674.cpp
// compile with: /clr /WX /W1 /LD
ref class G {
   int op_Implicit(int i) {   // C4674
      return 0;
   }
};
```
