---
title: Derleyici Uyarısı (Düzey 3) C4101
ms.date: 11/04/2016
f1_keywords:
- C4101
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
ms.openlocfilehash: d1109a32e754a6055e5e1d90632ad85332d832f1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402326"
---
# <a name="compiler-warning-level-3-c4101"></a>Derleyici Uyarısı (Düzey 3) C4101

'identifier': başvurulmayan yerel değişken

Yerel değişkeni hiçbir zaman kullanılmaz. Bu uyarı açık durumda gerçekleşir:

```
// C4101a.cpp
// compile with: /W3
int main() {
int i;   // C4101
}
```

Ancak, bu uyarı ayrıca çağırırken meydana gelir bir **statik** üye işlevi bir sınıf örneği ile:

```
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

Bu durumda, derleyici hakkında bilgileri kullanır `si` erişimi **statik** işlevi ama sınıfın örneğini gerekli değil çağrılacak **statik** işlev; bu nedenle uyarı. Bu uyarıyı gidermek için şunları yapabilirsiniz:

- Hangi derleyici kullandığınız örneği, bir oluşturucu ekleyin `si` çağrısında `func`.

- Kaldırma **statik** anahtar sözcüğü tanımından `func`.

- Çağrı **statik** açıkça işlev: `int y = S::func();`.