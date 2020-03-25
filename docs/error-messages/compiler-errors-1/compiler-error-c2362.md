---
title: Derleyici hatası C2362
ms.date: 06/03/2019
f1_keywords:
- C2362
helpviewer_keywords:
- C2362
ms.assetid: 7aafecbc-b3cf-45a6-9ec3-a17e3f222511
ms.openlocfilehash: 330932f53627f8ba09e9e089cec7809eeeb6ab1c
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80206082"
---
# <a name="compiler-error-c2362"></a>Derleyici hatası C2362

> '*Identifier*' öğesinin başlatılması ' Goto *Label*' tarafından atlandı

[/Za](../../build/reference/za-ze-disable-language-extensions.md)kullanılarak derlendiğinde, etikete yapılan bir atlamanın, tanımlayıcının başlatılmasını önler.

Bildirimin geçmiş bir blok ile veya değişken zaten başlatılmış bir blok içine alınmışsa, bir bildirimi yalnızca bir başlatıcı ile atlayabilirsiniz.

Aşağıdaki örnek C2362 oluşturur:

```cpp
// C2362.cpp
// compile with: /Za
int main() {
   goto label1;
   int i = 1;      // C2362, initialization skipped
label1:;
}
```

Olası çözüm:

```cpp
// C2362b.cpp
// compile with: /Za
int main() {
   goto label1;
   {
      int j = 1;   // OK, this block is never entered
   }
label1:;
}
```
