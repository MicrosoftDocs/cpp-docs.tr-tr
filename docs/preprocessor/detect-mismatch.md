---
title: detect_mismatch | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
dev_langs:
- C++
helpviewer_keywords:
- pragmas, detect_mismatch
- detect_mismatch pragma
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 55d7c3b81b3b8c43fb9024f2a58c27028950b144
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/25/2018
ms.locfileid: "50064179"
---
# <a name="detectmismatch"></a>detect_mismatch
Bir nesneyi bir kayıt yerleştirir. Bağlayıcı, bu kayıtları olası uyuşmazlıkları denetler.

## <a name="syntax"></a>Sözdizimi

```
#pragma detect_mismatch( "name", "value"))
```

## <a name="remarks"></a>Açıklamalar

Proje bağladığınızda, bağlayıcı oluşturur bir `LNK2038` proje aynı olan iki nesneleri içeriyorsa hata `name` ancak her farklı bir sahip `value`. Bu pragma, tutarsız nesne dosyaları önleme için kullanın.

Ad ve değer dize sabitleri dize ve dize sabit değerleri kaçış karakterleri ve birleştirme ile ilgili kurallara uyan. Büyük küçük harfe duyarlıdır ve virgül, eşittir işareti, tırnak işareti içeremez veya **null** karakter.

## <a name="example"></a>Örnek

Bu örnekte, aynı sürüm etiketi için farklı bir sürüm numaralarına sahip iki dosya oluşturulur.

```cpp
// pragma_directive_detect_mismatch_a.cpp
#pragma detect_mismatch("myLib_version", "9")
int main ()
{
   return 0;
}

// pragma_directive_detect_mismatch_b.cpp
#pragma detect_mismatch("myLib_version", "1")
```

Bu dosyaların her ikisini de komut satırını kullanarak derleme yaparsanız `cl pragma_directive_detect_mismatch_a.cpp pragma_directive_detect_mismatch_b.cpp`, hata alırsınız `LNK2038`.

## <a name="see-also"></a>Ayrıca Bkz.

[Pragma Yönergeleri ve __Pragma Anahtar Sözcüğü](../preprocessor/pragma-directives-and-the-pragma-keyword.md)