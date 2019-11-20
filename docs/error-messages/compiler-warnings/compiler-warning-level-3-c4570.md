---
title: Compiler Warning (level 3) C4570
ms.date: 11/04/2016
f1_keywords:
- C4570
helpviewer_keywords:
- C4570
ms.assetid: feec1225-e6ad-4995-8d96-c22e864a77bd
ms.openlocfilehash: fd144847ce6c4f8697cd866d304c23cb9b2be408
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/19/2019
ms.locfileid: "74188873"
---
# <a name="compiler-warning-level-3-c4570"></a>Compiler Warning (level 3) C4570

'type' : is not explicitly declared as abstract but has abstract functions

A type that contains [abstract](../../extensions/abstract-cpp-component-extensions.md) functions should itself be marked as abstract.

## <a name="example"></a>Örnek

The following sample generates C4570.

```cpp
// C4570.cpp
// compile with: /clr /W3 /c
ref struct X {   // C4570
// try the following line instead
// ref class X abstract {
   virtual void f() abstract;
};
```