---
title: Derleyici Hatası C2026 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2026
dev_langs:
- C++
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 055ac47d036a1027817aa6b3433bfe0e2e88570e
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46019555"
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