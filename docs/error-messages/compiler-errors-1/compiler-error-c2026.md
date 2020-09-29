---
title: Derleyici hatası C2026
description: Microsoft C/C++ derleyici hatası C2026, nedenlerini ve bunların nasıl çözümleneceğini açıklar.
ms.date: 09/25/2020
f1_keywords:
- C2026
helpviewer_keywords:
- C2026
ms.assetid: 8e64b6e1-b967-479b-be97-d12dc4a8e389
ms.openlocfilehash: 39195568f964f07c6131fa43ef4a0f06121795da
ms.sourcegitcommit: 94893973211d0b254c8bcdcf0779997dcc136b0c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/28/2020
ms.locfileid: "91414054"
---
# <a name="compiler-error-c2026"></a>Derleyici hatası C2026

> dize çok büyük, sondaki karakterler kesildi

Dize, 16380 tek baytlık karakter sınırından daha uzun.

## <a name="remarks"></a>Açıklamalar

Bitişik dizeler art arda alınmadan önce, bir dize 16380 tek baytlı karakterden daha uzun olamaz.

Bu uzunlukta bir yarısı yaklaşık bir Unicode dizesi de bu hatayı oluşturur.

## <a name="example"></a>Örnek

Aşağıdaki şekilde tanımlanmış bir dizeniz varsa, C2026 oluşturur:

```C
char sz[] =
"\
imagine a really, really \
long string here\
";
```

Bunu aşağıdaki gibi kesebilirsiniz:

```C
char sz[] =
"\
imagine a really, really "
"long string here\
";
```

Özel bir kaynakta veya harici bir dosyada, hariç tutulan büyük dize sabit değerlerini (32K veya daha fazla) depolamak isteyebilirsiniz. Daha fazla bilgi için, bkz. [Yeni bir özel veya veri kaynağı oluşturmak için](../../windows/binary-editor.md#to-create-a-new-custom-or-data-resource).
