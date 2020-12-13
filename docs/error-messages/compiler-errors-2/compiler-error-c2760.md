---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2760'
title: Derleyici hatası C2760
ms.date: 11/04/2016
f1_keywords:
- C2760
helpviewer_keywords:
- C2760
ms.assetid: 585757fd-d519-43f3-94e5-50316ac8b90b
ms.openlocfilehash: bba26b68a2e4c98cf478098b2e44e82962afd9f0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336159"
---
# <a name="compiler-error-c2760"></a>Derleyici hatası C2760

> sözdizimi hatası: '*name1*' bekleniyordu '*AD2*' değil

## <a name="remarks"></a>Açıklamalar

Bu hataya yol açabilecek birkaç yol vardır. Genellikle derleyicinin anlamlı yapamaması için bir belirteç sırası oluşur.

## <a name="example"></a>Örnek

Bu örnekte, bir atama işleci geçersiz bir işleçle kullanılır.

```cpp
// C2760.cpp
class B {};
class D : public B {};

void f(B* pb) {
    D* pd1 = static_cast<D*>(pb);
    D* pd2 = static_cast<D*>=(pb);  // C2760
    D* pd3 = static_cast<D*=(pb);   // C2760
}
```
