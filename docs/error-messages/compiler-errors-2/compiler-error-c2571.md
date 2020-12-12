---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2571'
title: Derleyici hatası C2571
ms.date: 11/04/2016
f1_keywords:
- C2571
helpviewer_keywords:
- C2571
ms.assetid: c6522616-dee9-4d7d-9bf8-30a7e1deaadf
ms.openlocfilehash: 773cab05204e15a22a4412364bd8f89cddfd92ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208976"
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
