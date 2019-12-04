---
title: Derleyici hatası C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: 2b57f3346427ff548d11fe776e909eca99433a81
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749041"
---
# <a name="compiler-error-c3908"></a>Derleyici hatası C3908

erişim düzeyi ' yapı ' değerinden daha az kısıtlayıcı

Özellik erişimcisi yönteminin (Get veya set), özelliğin kendisinde belirtilen erişime göre daha az kısıtlayıcı erişimi olamaz.  Benzer şekilde, olay erişimci yöntemleri için.

Daha fazla bilgi için bkz. [özellik](../../extensions/property-cpp-component-extensions.md) ve [olay](../../extensions/event-cpp-component-extensions.md).

Aşağıdaki örnek C3908 oluşturur:

```cpp
// C3908.cpp
// compile with: /clr
ref class X {
protected:
   property int i {
   public:   // C3908 property i is protected
      int get();
   private:
      void set(int);   // OK more restrictive
   };
};
```
