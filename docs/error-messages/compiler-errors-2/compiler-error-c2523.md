---
title: Derleyici Hatası C2523
ms.date: 11/04/2016
f1_keywords:
- C2523
helpviewer_keywords:
- C2523
ms.assetid: 7951b700-8f37-45a0-beb4-a79ae0ced72e
ms.openlocfilehash: 88a55a469fb8bc08d2ae73209c2e98a99dbc1df0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50482026"
---
# <a name="compiler-error-c2523"></a>Derleyici Hatası C2523

' sınıf:: ~ tanımlayıcı ': yıkıcı/Sonlandırıcı etiketi uyuşmazlığı

Yok edici adını bir tilde işareti tarafından öncesinde sınıf adı olmalıdır (`~`). Oluşturucu ve yıkıcı sınıfı aynı ada sahip yalnızca üyeleridir.

Aşağıdaki örnek, C2523 oluşturur:

```
// C2523.cpp
// compile with: /c
class A {
   ~B();    // C2523
   ~A();   // OK
};
```