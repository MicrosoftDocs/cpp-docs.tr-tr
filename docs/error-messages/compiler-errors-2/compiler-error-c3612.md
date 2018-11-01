---
title: Derleyici Hatası C3612
ms.date: 11/04/2016
f1_keywords:
- C3612
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
ms.openlocfilehash: a6084632ac0a84cc058ea73eb3c2b632208792eb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475939"
---
# <a name="compiler-error-c3612"></a>Derleyici Hatası C3612

'type': kapalı bir sınıf, soyut olamaz

Tarafından tanımlanan türleri `value` varsayılan olarak, korumalı ve sürece oluşturucularını tüm yöntemleri uygulayan bir sınıf soyuttur. Kapalı bir soyut sınıf bir temel sınıf diğerinden olabilir ya da oluşturulabilir.

Daha fazla bilgi için [sınıfları ve yapıları](../../windows/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3612 oluşturur:

```
// C3612.cpp
// compile with: /clr /c
value struct V: public System::ICloneable {};   // C3612

// OK
value struct V2: public System::ICloneable {
   Object^ Clone();
};
```