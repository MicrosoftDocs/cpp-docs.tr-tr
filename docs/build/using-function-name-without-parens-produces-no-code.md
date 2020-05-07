---
title: () Olmadan İşlev Adının Kullanılması Kod Üretmez
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
ms.openlocfilehash: 51be77dc8f4fe072ea6cc46dd51e38862649feda
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62314604"
---
# <a name="using-function-name-without--produces-no-code"></a>() Olmadan İşlev Adının Kullanılması Kod Üretmez

Programınızda bildirildiği bir işlev adı parantez olmadan kullanıldığında, derleyici kod oluşturmaz. Bu, derleyicinin işlev adresini hesaplamasından bağımsız olarak işlevin parametre alıp almadığına bakılmaksızın oluşur; Ancak, "()" işlev çağrısı işleci mevcut olmadığından, hiçbir çağrı yapılmaz. Bu sonuç aşağıdakine benzer:

```
// compile with /Wall to generate a warning
int a;
a;      // no code generated here either
```

Visual C++, uyarı düzeyi 4 ' ün kullanılması hiçbir Tanılama çıkışı oluşturmaz. Hiçbir uyarı verilmedi; kod üretilmedi.

Aşağıdaki örnek kod, hata olmadan (bir uyarı ile) ve bağlantılarla doğru şekilde derlenir, ancak başvuru içinde kod üretmez `funcn( )`. Bunun düzgün çalışması için "()" işlev çağrısı işlecini ekleyin.

```
#include <stdio.h>
void funcn();

int main() {
   funcn;      /* missing function call operator;
                  call will fail.  Use funcn() */
   }

void funcn() {
   printf("\nHello World\n");
}
```

## <a name="see-also"></a>Ayrıca bkz.

[Kodunuzu İyileştirme](optimizing-your-code.md)
