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

Programınızda bildirilen bir işlev adı parantez olmadan kullanıldığında, derleyici kod üretmez. Bu, derleyici bir işlevi adresi hesapladığından olup olmadığını işlevi parametre almayan bağımsız olarak gerçekleşir; Bununla birlikte, işlev çağrısı işleci (")" mevcut olmadığı için hiçbir çağrı yapılır. Bu sonuç aşağıdakine benzer olacaktır:

```
// compile with /Wall to generate a warning
int a;
a;      // no code generated here either
```

Visual C++'da, hatta uyarı düzeyi 4 kullanarak tanılama hiçbir çıktı oluşturur. Herhangi bir uyarı verilir; kod oluşturulur.

Aşağıdaki örnek kodu (bir uyarı ile) derler ve bağlantıları doğru bir şekilde hatasız ancak reference için kod üretmez `funcn( )`. Bunun düzgün çalışması için işlev çağrısı işleci (")" ekleyin.

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
