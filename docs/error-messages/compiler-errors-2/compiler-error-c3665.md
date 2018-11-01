---
title: Derleyici Hatası C3665
ms.date: 11/04/2016
f1_keywords:
- C3665
helpviewer_keywords:
- C3665
ms.assetid: 893bb47e-8de1-43aa-af7d-fa47ad149ee9
ms.openlocfilehash: 30aaf67ac9f912059bb5726681e61feabc1e557d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50644125"
---
# <a name="compiler-error-c3665"></a>Derleyici Hatası C3665

'yok edici': geçersiz kılma belirticisi 'anahtar sözcüğü yok Edicisi/sonlandırıcıda değiştiriciye izin verilmez'

Bir anahtar sözcüğü bir yıkıcı veya Sonlandırıcı verilmeyen kullanıldı.

Örneğin, yeni bir yuva bir yıkıcı veya Sonlandırıcı istenemez.  Daha fazla bilgi için [açık geçersiz kılmalar](../../windows/explicit-overrides-cpp-component-extensions.md) ve [yok ediciler ve sonlandırıcılar](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

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