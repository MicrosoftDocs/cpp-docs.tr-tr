---
title: Derleyici Hatası C2140 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2140
dev_langs:
- C++
helpviewer_keywords:
- C2140
ms.assetid: d44a0500-002c-4632-9e5e-c71c3a473ec4
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3fc0bd6fd0a43b8071a9872c9c1a598b57e090c3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46065406"
---
# <a name="compiler-error-c2140"></a>Derleyici Hatası C2140

'type': bir genel tür parametresine bağlı bir tür, derleyici iç tür niteliğine 'ayırt edici nitelik' bağımsız değişkeni olarak kullanılamaz

Geçersiz tür tanımlayıcısı için bir türü niteliğine geçirildi.

Daha fazla bilgi için [tür özellikleri için derleyici desteği](../../windows/compiler-support-for-type-traits-cpp-component-extensions.md).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C2140 oluşturur.

```
// C2140.cpp
// compile with: /clr /c
template <class T>

struct is_polymorphic {
   static const bool value = __is_polymorphic(T);
};

class x {};

generic <class T>
ref class C {
   void f() {
      System::Console::WriteLine(__is_polymorphic(T));   // C2140
      System::Console::WriteLine(is_polymorphic<T>::value);   // C2140

      System::Console::WriteLine(__is_polymorphic(x));   // OK
      System::Console::WriteLine(is_polymorphic<x>::value);   // OK
   }
};
```