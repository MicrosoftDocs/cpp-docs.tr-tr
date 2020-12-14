---
description: 'Hakkında daha fazla bilgi edinin: Derleyici Uyarısı (düzey 4) C4516'
title: Derleyici Uyarısı (düzey 4) C4516
ms.date: 11/04/2016
f1_keywords:
- C4516
helpviewer_keywords:
- C4516
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
ms.openlocfilehash: 945cf057b030a032afc2dd6dd3084df482f8a9a7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97241215"
---
# <a name="compiler-warning-level-4-c4516"></a>Derleyici Uyarısı (düzey 4) C4516

' class:: symbol ': erişim bildirimleri kullanım dışıdır; -bildirimleri kullanan üye daha iyi bir alternatif sağlar

ANSI C++ Komite, erişim bildirimlerini ( [using](../../cpp/using-declaration.md) anahtar sözcüğü olmadan türetilmiş bir sınıfın bir üyesinin erişimini değiştirme) güncel olmayan şekilde bildirdi. Erişim bildirimleri, C++ ' ın gelecek sürümleri tarafından desteklenmeyebilir.

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
