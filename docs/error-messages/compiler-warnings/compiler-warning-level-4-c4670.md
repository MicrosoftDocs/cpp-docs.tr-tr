---
title: Derleyici Uyarısı (düzey 4) C4670
ms.date: 11/04/2016
f1_keywords:
- C4670
helpviewer_keywords:
- C4670
ms.assetid: e172b134-b1fb-4dfe-8e9d-209ea08b73c7
ms.openlocfilehash: 3ea32e8693fbe310b82eeeb87b1e97f2281ddf04
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990756"
---
# <a name="compiler-warning-level-4-c4670"></a>Derleyici Uyarısı (düzey 4) C4670

' tanımlayıcı ': Bu taban sınıfına erişilemiyor

Bir **TRY** bloğunda oluşturulacak bir nesnenin belirtilen temel sınıfına erişilemiyor. Nesne oluşturulursa, nesne örneği oluşturulamıyor. Temel sınıfın doğru erişim belirticisiyle devralındığından emin olun.

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
