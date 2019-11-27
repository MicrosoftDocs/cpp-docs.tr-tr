---
title: Derleyici Uyarısı (düzey 4) C4100
ms.date: 11/04/2016
f1_keywords:
- C4100
helpviewer_keywords:
- C4100
ms.assetid: 478ed97d-e502-49e4-9afb-ac2a6c61194b
ms.openlocfilehash: 80794d270b40a8f40d44630da70455c015158423
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541237"
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