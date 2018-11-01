---
title: Derleyici Hatası C2650
ms.date: 11/04/2016
f1_keywords:
- C2650
helpviewer_keywords:
- C2650
ms.assetid: 49a8ac6e-aa6d-4616-917c-a3cfcdbad5a4
ms.openlocfilehash: c7cbc12bff4e00613032a9d28b5be7533dce9612
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50608007"
---
# <a name="compiler-error-c2650"></a>Derleyici Hatası C2650

'operator': bir sanal işlev olamaz

A `new` veya `delete` işleci bildirilmiş `virtual`. Bu işleçler `static` üye işlevleri ve olamaz `virtual`.

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2650 oluşturur:

```
// C2650.cpp
// compile with: /c
class A {
   virtual void* operator new( unsigned int );   // C2650
   // try the following line instead
   // void* operator new( unsigned int );
};
```