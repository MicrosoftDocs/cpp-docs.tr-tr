---
title: () Kod üretmez olmadan işlev adının kullanılması | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions [C++], without parentheses
ms.assetid: edf4a177-a160-44aa-8436-e077b5b27809
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 13ca43386c9ef46f526538781a91fd1a81ade537
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/17/2018
ms.locfileid: "45710586"
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

## <a name="see-also"></a>Ayrıca Bkz.

[Kodunuzu İyileştirme](../../build/reference/optimizing-your-code.md)