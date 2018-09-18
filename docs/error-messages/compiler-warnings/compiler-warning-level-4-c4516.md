---
title: Derleyici Uyarısı (düzey 4) C4516 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4516
dev_langs:
- C++
helpviewer_keywords:
- C4516
ms.assetid: 6677bb1f-d26e-4ab9-8644-6b5a2a8f4ff8
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 88bb2232c635a89650be892a27e490a42d7197ca
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045633"
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