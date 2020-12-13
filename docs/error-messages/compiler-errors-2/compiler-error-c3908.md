---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3908'
title: Derleyici hatası C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: 67258f9f5946d180af9a270b931f88f263238856
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97144176"
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
