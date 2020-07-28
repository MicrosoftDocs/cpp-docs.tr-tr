---
title: Derleyici hatası C2793
ms.date: 11/04/2016
f1_keywords:
- C2793
helpviewer_keywords:
- C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
ms.openlocfilehash: faf87334f1a98661078341a4d7dc11280802a376
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220216"
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
