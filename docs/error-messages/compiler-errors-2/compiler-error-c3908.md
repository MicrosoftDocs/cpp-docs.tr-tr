---
title: Derleyici Hatası C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: 84b21f20cbc8203a9cd70e487738c34c6ad3a89b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598940"
---
# <a name="compiler-error-c3908"></a>Derleyici Hatası C3908

'yapısı' daha az kısıtlayıcı erişim düzeyi

Bir özellik erişimci yöntemini (get veya set) özelliği üzerinde belirtilen erişim'den daha az kısıtlayıcı erişim sahip olamaz.  Olay erişimci metotları için benzer şekilde.

Daha fazla bilgi için [özelliği](../../windows/property-cpp-component-extensions.md) ve [olay](../../windows/event-cpp-component-extensions.md).

Aşağıdaki örnek, C3908 oluşturur:

```
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