---
description: 'Hakkında daha fazla bilgi: derleyici hatası C2793'
title: Derleyici hatası C2793
ms.date: 11/04/2016
f1_keywords:
- C2793
helpviewer_keywords:
- C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
ms.openlocfilehash: 26d38427f8d5b502df7d8a6ff4351dd00a3155eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297752"
---
# <a name="compiler-error-c2793"></a>Derleyici hatası C2793

' token ': ':: ', Identifier veya anahtar sözcüğü ' operator ' sonrasında beklenmeyen belirteç bekleniyor

Yalnızca `__super::` bir tanımlayıcı ya da anahtar sözcük olabilir **`operator`** .

Aşağıdaki örnek C2793 oluşturur

```cpp
// C2793.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super::(); // C2793
   }
};
```
