---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2724'
title: Derleyici hatası C2724
ms.date: 11/04/2016
f1_keywords:
- C2724
helpviewer_keywords:
- C2724
ms.assetid: 4e4664bc-8c96-4156-b79f-03436f532ea8
ms.openlocfilehash: c11ac7521528446504a74e0f6f22c1ea24735626
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155507"
---
# <a name="compiler-error-c2724"></a>Derleyici hatası C2724

' tanımlayıcı ': ' static ' dosya kapsamında tanımlanan üye işlevlerde kullanılmamalıdır

Statik üye işlevleri dış bağlantı ile bildirilmelidir.

Aşağıdaki örnek C2724 oluşturur:

```cpp
// C2724.cpp
class C {
   static void func();
};

static void C::func(){};   // C2724
// try the following line instead
// void C::func(){};
```
