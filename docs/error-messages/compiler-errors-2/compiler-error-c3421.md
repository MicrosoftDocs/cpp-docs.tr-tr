---
title: Derleyici Hatası C3421 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3421
dev_langs:
- C++
helpviewer_keywords:
- C3421
ms.assetid: b52050c6-17a4-424a-8894-337b0cec7010
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 815fc64e1f2cc80440e188d944827820bd55383b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46114546"
---
# <a name="compiler-error-c3421"></a>Derleyici Hatası C3421

'type': ya da olduğu gibi bu sınıf için Sonlandırıcı çağrılamıyor erişilemez veya artık yok

Bir sonlandırıcı örtük olarak özel olduğundan, gelen kapsayan türdeki dışında çağrılamaz.

Daha fazla bilgi için [yok ediciler ve sonlandırıcılar, nasıl yapılır: sınıfları ve yapıları tanımlama ve kullanma (C + +/ CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Örnek

Aşağıdaki örnek, C3421 oluşturur.

```
// C3421.cpp
// compile with: /clr
ref class A {};

ref class B {
   !B() {}

public:
   ~B() {}
};

int main() {
   A a;
   a.!A();   // C3421

   B b;
   b.!B();   // C3421
}
```