---
title: Derleyici Uyarısı (düzey 3) C4101
ms.date: 11/04/2016
f1_keywords:
- C4101
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
ms.openlocfilehash: 0ac34fbaf4cbb54583394dff5b8645fe56b8b9cd
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199052"
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
