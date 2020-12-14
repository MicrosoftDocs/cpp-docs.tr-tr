---
description: 'Hakkında daha fazla bilgi: derleyici hatası C3612'
title: Derleyici hatası C3612
ms.date: 11/04/2016
f1_keywords:
- C3612
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
ms.openlocfilehash: 332d4bae940a0c98b148fd6ba951a4f51d1bee27
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223106"
---
# <a name="compiler-error-c3612"></a>Derleyici hatası C3612

' Type ': Sealed bir sınıf abstract olamaz

Kullanılarak tanımlanan türler `value` Varsayılan olarak korumalıdır ve temel aldığı tüm yöntemleri uygulamadıkça bir sınıf soyuttur. Sealed bir soyut sınıf, temel sınıf olamaz, ya da oluşturulabilir.

Daha fazla bilgi için bkz. [sınıflar ve yapılar](../../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek C3612 oluşturur:

```cpp
// C3612.cpp
// compile with: /clr /c
value struct V: public System::ICloneable {};   // C3612

// OK
value struct V2: public System::ICloneable {
   Object^ Clone();
};
```
