---
title: Derleyici hatası C3896
ms.date: 11/04/2016
f1_keywords:
- C3896
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
ms.openlocfilehash: f15cd73465f4210ed5e5e34bebe2122c0b88f722
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749275"
---
# <a name="compiler-error-c3896"></a>Derleyici hatası C3896

' üye ': Hatalı Başlatıcı: Bu sabit değerli veri üyesi yalnızca ' nullptr ' ile başlatılabilir

[Sabit değerli](../../extensions/literal-cpp-component-extensions.md) bir veri üyesi yanlış başlatılmış.  Daha fazla bilgi için bkz. [nullptr](../../extensions/nullptr-cpp-component-extensions.md) .

Aşağıdaki örnek C3896 oluşturur:

```cpp
// C3896.cpp
// compile with: /clr /c
ref class R{};

value class V {
   literal R ^ r = "test";   // C3896
   literal R ^ r2 = nullptr;   // OK
};
```
