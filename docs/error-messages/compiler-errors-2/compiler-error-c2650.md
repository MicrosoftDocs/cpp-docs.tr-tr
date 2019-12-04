---
title: Derleyici hatası C2650
ms.date: 11/04/2016
f1_keywords:
- C2650
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
ms.openlocfilehash: f71996c6d04d8be2101762fb0fb17634e6b25a1a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74756142"
---
# <a name="compiler-error-c2650"></a>Derleyici hatası C2650

' operator ': sanal işlev olamaz

Bir `new` veya `delete` işleci `virtual`olarak bildirilmiştir. Bu işleçler `static` üye işlevleridir ve `virtual`olamaz.

## <a name="example"></a>Örnek

Aşağıdaki örnek C2650 oluşturur:

```cpp
// C2650.cpp
// compile with: /c
class A {
   virtual void* operator new( unsigned int );   // C2650
   // try the following line instead
   // void* operator new( unsigned int );
};
```
