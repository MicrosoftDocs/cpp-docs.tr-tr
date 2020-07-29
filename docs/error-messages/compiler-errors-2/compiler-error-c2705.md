---
title: Derleyici hatası C2705
ms.date: 11/04/2016
f1_keywords:
- C2705
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
ms.openlocfilehash: 65d9ed2458f43e6c9a697be02ffc9b831259624c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225442"
---
# <a name="compiler-error-c2705"></a>Derleyici hatası C2705

' etiket ': ' Exception Handler bloğu ' kapsamına geçersiz zıplama

Yürütme,, blok içindeki bir etikete atlar **`try`** / **`catch`** `__try` / **`__except`** `__try` / **`__finally`** . Daha fazla bilgi için bkz. [özel durum işleme](../../cpp/exception-handling-in-visual-cpp.md).

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
