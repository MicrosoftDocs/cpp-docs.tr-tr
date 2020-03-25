---
title: Derleyici hatası C2026
ms.date: 11/04/2016
f1_keywords:
- C2026
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
ms.openlocfilehash: 9747b1edadc76ceeb502b2c6fd03496b91769f5a
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/24/2020
ms.locfileid: "80208071"
---
# <a name="compiler-error-c2026"></a>Derleyici hatası C2026

dize çok büyük, sondaki karakterler kesildi

Dize, 16380 tek baytlık karakter sınırından daha uzun.

Art arda eklenen dizelerin öncesinde, bir dize 16380 tek baytlı karakterden daha uzun olamaz.

Bu uzunlukta bir yarısı yaklaşık bir Unicode dizesi de bu hatayı oluşturur.

Aşağıdaki şekilde tanımlanmış bir dizeniz varsa, C2026 oluşturur:

```
char sz[] =
"\
imagine a really, really \
long string here\
";
```

Bunu aşağıdaki gibi kesebilirsiniz:

```
char sz[] =
"\
imagine a really, really "
"long string here\
";
```

Özel bir kaynakta veya harici bir dosyada, hariç tutulan büyük dize sabit değerlerini (32K veya daha fazla) depolamak isteyebilirsiniz. Daha fazla bilgi için bkz. [Yeni bir özel veya veri kaynağı oluşturma](../../windows/creating-a-new-custom-or-data-resource.md) .
