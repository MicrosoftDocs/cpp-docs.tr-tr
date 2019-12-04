---
title: Derleyici hatası C2793
ms.date: 11/04/2016
f1_keywords:
- C2793
helpviewer_keywords:
- C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
ms.openlocfilehash: 5b8712473631b16e2bbb47430966ccc0c552b9df
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739395"
---
# <a name="compiler-error-c2793"></a>Derleyici hatası C2793

' token ': ':: ', Identifier veya anahtar sözcüğü ' operator ' sonrasında beklenmeyen belirteç bekleniyor

Yalnızca `__super::` `operator`bir tanımlayıcı ya da anahtar sözcük olan belirteçleri kullanabilirsiniz.

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
