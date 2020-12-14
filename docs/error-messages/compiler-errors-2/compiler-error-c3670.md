---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3670'
title: Derleyici hatası C3670
ms.date: 11/04/2016
f1_keywords:
- C3670
helpviewer_keywords:
- C3670
ms.assetid: d0fa9c6e-8f90-48c7-9066-31b4fa5942eb
ms.openlocfilehash: 499ef1a8f0638da7693ccdbdc0b02c0d5c86c59b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228943"
---
# <a name="compiler-error-c3670"></a>Derleyici hatası C3670

' override ': erişilemeyen temel sınıf yöntemi ' Method ' geçersiz kılınamaz

Bir geçersiz kılma, yalnızca erişim düzeyi türetilmiş bir türde kullanılabilir hale getiren bir işlevde gerçekleşebilir. Daha fazla bilgi için bkz. [Açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md).

Aşağıdaki örnek C3670 oluşturur:

```cpp
// C3670.cpp
// compile with: /clr /c
public ref class C {
// Uncomment the following line to resolve.
// public:
   virtual void g() { }
};

public ref class D : public C {
public:
   virtual void f() new sealed = C::g {};   // C3670
};
```
