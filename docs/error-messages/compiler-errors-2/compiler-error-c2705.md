---
title: Derleyici Hatası C2705
ms.date: 11/04/2016
f1_keywords:
- C2705
helpviewer_keywords:
- C2705
ms.assetid: 29249ea3-4ea7-4105-944b-bdb83e8d6852
ms.openlocfilehash: 872471158d3f8c301a271dd68b2ef36839e2b9c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50616277"
---
# <a name="compiler-error-c2705"></a>Derleyici Hatası C2705

'etiketi': 'özel durum işleyici Bloğu' kapsamı içine geçersiz atlama

Yürütme atlar içinde bir etikete bir `try` / `catch`, `__try` / `__except`, `__try` / `__finally` blok. Daha fazla bilgi için [özel durum işleme](../../cpp/exception-handling-in-visual-cpp.md).

Aşağıdaki örnek, C2705 oluşturur:

```
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