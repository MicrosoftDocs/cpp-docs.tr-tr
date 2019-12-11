---
title: Derleyici Uyarısı (düzey 4) C4516
ms.date: 11/04/2016
f1_keywords:
- C4516
helpviewer_keywords:
- C4516
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
ms.openlocfilehash: 47e278bbc69b972f6acc391d6b3278ab8d159c08
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74990695"
---
# <a name="compiler-warning-level-4-c4516"></a>Derleyici Uyarısı (düzey 4) C4516

' class:: symbol ': erişim bildirimleri kullanım dışıdır; -bildirimleri kullanan üye daha iyi bir alternatif sağlar

ANSI C++ Komite, erişim bildirimlerini ( [using](../../cpp/using-declaration.md) anahtar sözcüğü olmadan türetilmiş bir sınıfta bir üyenin erişimini değiştirerek) güncel olmayan şekilde bildirdi. Erişim bildirimleri gelecekteki sürümleri tarafından desteklenmiyor olabilir C++.

Aşağıdaki örnek C4516 oluşturur:

```cpp
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
