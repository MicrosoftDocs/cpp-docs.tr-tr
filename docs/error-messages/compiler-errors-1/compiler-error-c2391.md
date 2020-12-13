---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2391'
title: Derleyici hatası C2391
ms.date: 11/04/2016
f1_keywords:
- C2391
helpviewer_keywords:
- C2391
ms.assetid: 63a9c6b9-03cc-4517-885c-bdcd048643b3
ms.openlocfilehash: 3161cd6ade15817142cc24f38c61fd3e09eb8857
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337583"
---
# <a name="compiler-error-c2391"></a>Derleyici hatası C2391

' tanımlayıcı ': ' Friend ' tür tanımı sırasında kullanılamaz

**`friend`** Bildirim, bir bütün sınıf bildirimi içerir. Bir **`friend`** bildirim, bir üye işlevi veya bir ayrıntılı tür belirleyicisi belirtebilir, ancak bir sınıf bildirimi içeremez.

Aşağıdaki örnek C2326 oluşturur:

```cpp
// C2391.cpp
// compile with: /c
class D {
   void func( int );
};

class A {
   friend class B { int i; };   // C2391

   // OK
   friend class C;
   friend void D::func(int);
};
```
