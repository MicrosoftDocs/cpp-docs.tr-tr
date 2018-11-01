---
title: Derleyici Uyarısı (düzey 4) C4516
ms.date: 11/04/2016
f1_keywords:
- C4516
helpviewer_keywords:
- C4516
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
ms.openlocfilehash: 8020103e8e20bf1a5e955cbfdfafc6a328b439e6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50564053"
---
# <a name="compiler-warning-level-4-c4516"></a>Derleyici Uyarısı (düzey 4) C4516

'class::symbol': erişim bildirimleri kullanımdan; üye kullanarak-bildirim kullanımları daha iyi bir alternatif sağlıyor

ANSI C++ komitesi erişim bildirimleri bildirdiği (türetilen bir sınıfta bir üyenin erişim değiştirme [kullanarak](../../cpp/using-declaration.md) anahtar sözcüğü) güncelliğini yitirmiş. Erişim bildirimleri C++ gelecekteki sürümleri tarafından desteklenmiyor olabilir.

Aşağıdaki örnek, C4516 oluşturur:

```
// C4516.cpp
// compile with: /W4
class A
{
public:
   void x(char);
};

class B : protected A
{
public:
   A::x;  // C4516 on access-declaration
   // use the following line instead
   // using A::x; // using-declaration, ok
};

int main()
{
}
```