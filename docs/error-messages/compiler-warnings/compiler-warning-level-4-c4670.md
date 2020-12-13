---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4670'
title: Derleyici Uyarısı (düzey 4) C4670
ms.date: 11/04/2016
f1_keywords:
- C4670
helpviewer_keywords:
- C4670
ms.assetid: e172b134-b1fb-4dfe-8e9d-209ea08b73c7
ms.openlocfilehash: c1d0f81f10fe63882987d660e4b9099f4ff895ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97134036"
---
# <a name="compiler-warning-level-4-c4670"></a>Derleyici Uyarısı (düzey 4) C4670

' tanımlayıcı ': Bu taban sınıfına erişilemiyor

Bir blokta oluşturulacak bir nesnenin belirtilen temel sınıfına **`try`** erişilemiyor. Nesne oluşturulursa, nesne örneği oluşturulamıyor. Temel sınıfın doğru erişim belirticisiyle devralındığından emin olun.

Aşağıdaki örnek C4670 oluşturur:

```cpp
// C4670.cpp
// compile with: /EHsc /W4
class A
{
};

class B : /* public */ A
{
} b;   // inherits A with private access by default

int main()
{
    try
    {
       throw b;   // C4670
    }
    catch( B )
    {
    }
}
```
