---
title: detect_mismatch
ms.date: 11/04/2016
f1_keywords:
- vc-pragma.detect_mismatch
- detect_mismatch_CPP
helpviewer_keywords:
- pragmas, detect_mismatch
- detect_mismatch pragma
ms.assetid: ddb13ac9-0e2f-40ce-be69-7e44c04f5a12
ms.openlocfilehash: 2973a4738aa54e9f454190b18bcabff92077b284
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633330"
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