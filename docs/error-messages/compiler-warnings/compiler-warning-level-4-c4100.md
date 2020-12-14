---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4100'
title: Derleyici Uyarısı (düzey 4) C4100
ms.date: 11/04/2016
f1_keywords:
- C4100
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
ms.openlocfilehash: 753be5e6e56e4ad94d6b742454fe62e303d430dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262002"
---
# <a name="compiler-warning-level-4-c4100"></a>Derleyici Uyarısı (düzey 4) C4100

' tanımlayıcı ': başvurulmayan biçimsel parametre

Biçimsel parametreye işlevin gövdesinde başvurulmuyor. Başvurulmayan parametre yoksayıldı.

Kod, diğer bir deyişle, diğer bir deyişle, bir temel türün başvurulmayan parametresi üzerinde bir yıkıcıya çağırdığında da verilebilir.  Bu, Microsoft C++ derleyicisi kısıtlamasıdır.

Aşağıdaki örnek C4100 oluşturur:

```cpp
// C4100.cpp
// compile with: /W4
void func(int i) {   // C4100, delete the unreferenced parameter to
                     //resolve the warning
   // i;   // or, add a reference like this
}

int main()
{
   func(1);
}
```
