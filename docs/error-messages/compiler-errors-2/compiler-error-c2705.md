---
title: Derleyici hatası C2705
ms.date: 11/04/2016
f1_keywords:
- C2705
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
ms.openlocfilehash: 1cd46db8e4cb237bebd9568409ecadf0ff84cdf8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758313"
---
# <a name="compiler-error-c2705"></a>Derleyici hatası C2705

' etiket ': ' Exception Handler bloğu ' kapsamına geçersiz zıplama

Yürütme, bir `try`/`catch`, `__try`/`__except``__try`/blok içindeki bir etikete atlar. Daha fazla bilgi için bkz. [özel durum işleme](../../cpp/exception-handling-in-visual-cpp.md).

Aşağıdaki örnek C2705 oluşturur:

```cpp
// C2705.cpp
int main() {
goto trouble;
   __try {
      trouble: ;   // C2705
   }
   __finally {}

   // try the following line instead
   // trouble: ;
}
```
