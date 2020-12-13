---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 1) C4674'
title: Derleyici Uyarısı (düzey 1) C4674
ms.date: 11/04/2016
f1_keywords:
- C4674
helpviewer_keywords:
- C4674
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
ms.openlocfilehash: 1df7dd982f52a6987e06e888130953c1a9deb330
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334972"
---
# <a name="compiler-warning-level-1-c4674"></a>Derleyici Uyarısı (düzey 1) C4674

' Method ', ' static ' olarak bildirilmelidir ve tam olarak bir parametreye sahip olmalıdır

Bir dönüştürme işlecinin imzası doğru değildi. Yöntem, Kullanıcı tanımlı bir dönüştürme olarak kabul edilmez. İşleçleri tanımlama hakkında daha fazla bilgi için bkz. [Kullanıcı tanımlı işleçler (c++/CLI)](../../dotnet/user-defined-operators-cpp-cli.md) ve [Kullanıcı tanımlı dönüşümler (c++/CLI)](../../dotnet/user-defined-conversions-cpp-cli.md).

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
