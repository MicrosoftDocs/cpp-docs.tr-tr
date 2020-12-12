---
description: 'Hakkında daha fazla bilgi edinin: () olmadan Işlev adının kullanılması kod üretmez'
title: () Olmadan İşlev Adının Kullanılması Kod Üretmez
ms.date: 11/04/2016
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
ms.openlocfilehash: 1fedc296422a759878c26469ccc20955043b3913
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97277264"
---
# <a name="using-function-name-without--produces-no-code"></a>() Olmadan İşlev Adının Kullanılması Kod Üretmez

Programınızda bildirildiği bir işlev adı parantez olmadan kullanıldığında, derleyici kod oluşturmaz. Bu, derleyicinin işlev adresini hesaplamasından bağımsız olarak işlevin parametre alıp almadığına bakılmaksızın oluşur; Ancak, "()" işlev çağrısı işleci mevcut olmadığından, hiçbir çağrı yapılmaz. Bu sonuç aşağıdakine benzer:

```
// compile with /Wall to generate a warning
int a;
a;      // no code generated here either
```

Visual C++, uyarı düzeyi 4 ' ün kullanılması hiçbir Tanılama çıkışı oluşturmaz. Hiçbir uyarı verilmedi; kod üretilmedi.

Aşağıdaki örnek kod, hata olmadan (bir uyarı ile) ve bağlantılarla doğru şekilde derlenir, ancak başvuru içinde kod üretmez `funcn( )` . Bunun düzgün çalışması için "()" işlev çağrısı işlecini ekleyin.

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

[Kodunuzu iyileştirme](optimizing-your-code.md)
