---
title: Derleyici Uyarısı (düzey 3) C4570
ms.date: 11/04/2016
f1_keywords:
- C4570
helpviewer_keywords:
- C4570
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
ms.openlocfilehash: 13767cdbd34c72953568181c15ad33119bf5179a
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991935"
---
# <a name="compiler-warning-level-3-c4570"></a>Derleyici Uyarısı (düzey 3) C4570

' Type ': açıkça soyut olarak bildirilmemiş ancak soyut işlevlere sahip

[Soyut](../../extensions/abstract-cpp-component-extensions.md) işlevler içeren bir türün kendisi soyut olarak işaretlenmelidir.

## <a name="example"></a>Örnek

Aşağıdaki örnek C4570 oluşturur.

```cpp
// C4570.cpp
// compile with: /clr /W3 /c
ref struct X {   // C4570
// try the following line instead
// ref class X abstract {
   virtual void f() abstract;
};
```
