---
title: Derleyici Hatası C2026
ms.date: 11/04/2016
f1_keywords:
- C2026
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
ms.openlocfilehash: da4c03c681f95efaa5edb159869315b41d027e99
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50657141"
---
# <a name="compiler-error-c2026"></a>Derleyici Hatası C2026

dize çok büyük, sondaki karakterler kesildi

Dize 16380 tek baytlık karakter sınırından daha uzun.

Birleştirilmiş bitişik dize önce bir dize 16380 tek baytlık karakterden uzun olamaz.

Bu süre yaklaşık yarım Unicode dizesi de bu hata oluşturur.

Şu şekilde tanımlanmış bir dize varsa C2026 oluşturur:

```
char sz[] =
"\
imagine a really, really \
long string here\
";
```

Bunu şu şekilde bölmek:

```
char sz[] =
"\
imagine a really, really "
"long string here\
";
```

Olağanüstü bir geniş dize değişmez değerleri (32 bin veya daha fazlası) depolamak özel bir kaynak veya bir dış dosya isteyebilirsiniz. Bkz: [yeni özel veya veri kaynağı oluşturma](../../windows/creating-a-new-custom-or-data-resource.md) daha fazla bilgi için.