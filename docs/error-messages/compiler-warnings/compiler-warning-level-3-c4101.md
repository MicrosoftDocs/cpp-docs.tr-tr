---
title: Derleyici Uyarısı (Düzey 3) C4101 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4101
dev_langs:
- C++
helpviewer_keywords:
- C4101
ms.assetid: d98563cd-9dce-4aae-8f12-bd552a4ea677
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1549a327329d438cb30bd6908e07419eb1b6bc1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46060843"
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