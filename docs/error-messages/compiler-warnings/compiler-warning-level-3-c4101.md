---
title: Derleyici Uyarısı (düzey 3) C4101
ms.date: 11/04/2016
f1_keywords:
- C4101
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
ms.openlocfilehash: 5effdbb4c7e83999655641a248c389c7c4d260d0
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051897"
---
# <a name="compiler-warning-level-3-c4101"></a>Derleyici Uyarısı (düzey 3) C4101

' tanımlayıcı ': başvurulmayan yerel değişken

Yerel değişken hiç kullanılmıyor. Bu uyarı belirgin durumda gerçekleşir:

```cpp
// C4101a.cpp
// compile with: /W3
int main() {
int i;   // C4101
}
```

Ancak, bu uyarı bir **statik** üye işlevini sınıfın bir örneği aracılığıyla çağırırken da meydana gelir:

```cpp
// C4101b.cpp
// compile with:  /W3
struct S {
   static int func()
   {
      return 1;
   }
};

int main() {
   S si;   // C4101, si is never used
   int y = si.func();
   return y;
}
```

Bu durumda, derleyici **statik** işleve erişmek için `si` hakkındaki bilgileri kullanır, ancak sınıfının örneği **statik** işlevi çağırmak için gerekli değildir; Bu nedenle uyarı. Bu uyarıyı çözmek için şunları yapabilirsiniz:

- Derleyicinin `func`çağrısında `si` örneğini kullanacağı bir Oluşturucu ekleyin.

- **Statik** anahtar sözcüğünü `func`tanımından kaldırın.

- **Statik** işlevi açıkça çağırın: `int y = S::func();`.