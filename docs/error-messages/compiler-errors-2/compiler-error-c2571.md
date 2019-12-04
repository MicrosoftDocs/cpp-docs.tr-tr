---
title: Derleyici hatası C2571
ms.date: 11/04/2016
f1_keywords:
- C2571
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
ms.openlocfilehash: 7bd87f0732e1a632b8c86cc57fab1a0f104b2c77
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755505"
---
# <a name="compiler-error-c2571"></a>Derleyici hatası C2571

' function ': sanal işlev ' Union ' birleşimi içinde olamaz

Bir bileşim bir sanal işlevle birlikte bildirilmiştir. Bir sanal işlevi yalnızca bir sınıf veya yapıda bildirebilirsiniz.  Olası çözümler:

1. Birleşimi bir sınıfa veya yapıya değiştirin.

1. İşlevi sanal olmayan hale getirin.

Aşağıdaki örnek C2571 oluşturur:

```cpp
// C2571.cpp
// compile with: /c
union A {
   virtual void func1();   // C2571
   void func2();   // OK
};
```
