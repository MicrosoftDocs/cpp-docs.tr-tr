---
title: Derleyici Hatası C3908
ms.date: 11/04/2016
f1_keywords:
- C3908
helpviewer_keywords:
- C3908
ms.assetid: 3c322482-c79e-4197-a578-2ad9bc379d1a
ms.openlocfilehash: e11d830c3d662ea424caadeb50df669700f8c78f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58766761"
---
# <a name="compiler-error-c3908"></a>Derleyici Hatası C3908

'yapısı' daha az kısıtlayıcı erişim düzeyi

Bir özellik erişimci yöntemini (get veya set) özelliği üzerinde belirtilen erişim'den daha az kısıtlayıcı erişim sahip olamaz.  Olay erişimci metotları için benzer şekilde.

Daha fazla bilgi için [özelliği](../../extensions/property-cpp-component-extensions.md) ve [olay](../../extensions/event-cpp-component-extensions.md).

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