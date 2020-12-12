---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 2) C4285'
title: Derleyici Uyarısı (düzey 2) C4285
ms.date: 11/04/2016
f1_keywords:
- C4285
helpviewer_keywords:
- C4285
ms.assetid: fa14de1f-fc19-4eec-8bea-81003636e12f
ms.openlocfilehash: 2eafb9bb17c5e6ea782ff00900c410727b3b39f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97173590"
---
# <a name="compiler-warning-level-2-c4285"></a>Derleyici Uyarısı (düzey 2) C4285

' Identifier:: operator-> ' için dönüş türü, indüzeltilme gösterimi kullanılarak uygulanırsa özyinelemeli

Belirtilen **operator-> ()** işlevi, tanımlandığı türü veya tanımlandığı türe bir başvuru döndüremez.

Aşağıdaki örnek C4285 oluşturur:

```cpp
// C4285.cpp
// compile with: /W2
class C
{
public:
    C operator->();   // C4285
   // C& operator->();  C4285, also
};

int main()
{
}
```
