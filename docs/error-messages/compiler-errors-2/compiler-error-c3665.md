---
title: Derleyici Hatası C3665
ms.date: 11/04/2016
f1_keywords:
- C3665
helpviewer_keywords:
- C3665
ms.assetid: 893bb47e-8de1-43aa-af7d-fa47ad149ee9
ms.openlocfilehash: 40de7a7b1ede5e6dbbc20d2128b782c0ad6f798b
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/01/2019
ms.locfileid: "58781035"
---
# <a name="compiler-error-c3665"></a>Derleyici Hatası C3665

'yok edici': geçersiz kılma belirticisi 'anahtar sözcüğü yok Edicisi/sonlandırıcıda değiştiriciye izin verilmez'

Bir anahtar sözcüğü bir yıkıcı veya Sonlandırıcı verilmeyen kullanıldı.

Örneğin, yeni bir yuva bir yıkıcı veya Sonlandırıcı istenemez.  Daha fazla bilgi için [açık geçersiz kılmalar](../../extensions/explicit-overrides-cpp-component-extensions.md) ve [yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

Aşağıdaki örnek, C3665 oluşturur:

```
// C3665.cpp
// compile with: /clr
public ref struct R {
   virtual ~R() { }
   virtual void a() { }
};

public ref struct S : R {
   virtual ~S() new {}   // C3665
   virtual void a() new {}   // OK
};
```