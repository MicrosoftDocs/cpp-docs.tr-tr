---
title: Derleyici Hatası C2253 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2253
dev_langs:
- C++
helpviewer_keywords:
- C2253
ms.assetid: bd6445ae-b2c1-4669-9657-a8f4acf80b16
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1bb9c78551195c1f451e9aa982c5ecc1a19c71d6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46072348"
---
# <a name="compiler-error-c2253"></a>Derleyici Hatası C2253

'function': Saf belirtici veya soyut geçersiz kılma belirticisi yalnızca sanal işlev üzerinde izin verilir

Sanal olmayan bir işlev olarak saf belirtilen `virtual`.

Aşağıdaki örnek, C2253 oluşturur:

```
// C2253.cpp
// compile with: /c
class A {
public:
   void func1() = 0;   // C2253 not virtual
   virtual void func2() = 0;   // OK
};
```

Aşağıdaki örnek, C2253 oluşturur:

```
// C2253_2.cpp
// compile with: /clr /c
ref struct A {
   property int Prop_3 {
      int get() abstract;   // C2253
      // try the following line instead
      // virtual int get() abstract;

      void set(int i) abstract;   // C2253
      // try the following line instead
      // virtual void set(int i) abstract;
   }
};
```