---
description: 'Hakkında daha fazla bilgi edinin: chars_format Enum'
title: chars_format sabit listesi
ms.date: 08/03/2020
f1_keywords:
- charconv/std::chars_format
helpviewer_keywords:
- std::chars_format
ms.openlocfilehash: af458f96e3e9dbe4db9d1adab1c529403cefcaa6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97325187"
---
# <a name="chars_format-enum"></a>chars_format sabit listesi

[\<charconv>](charconv.md)Basit sayısal dönüşümler için kayan nokta biçimini belirtmek üzere kitaplığıyla birlikte kullanılır.

## <a name="syntax"></a>Syntax

```cpp
enum class chars_format {
    scientific = unspecified,
    fixed = unspecified,
    hex = unspecified,
    general = fixed | scientific
};
```

### <a name="members"></a>Üyeler

|Öğe|Açıklama|
|-|-|
| `scientific` | `from_chars()`Bir üs beklenmesine ve ayrıştırmasına neden olur. Bu, `printf()` `'e'` gibi bilimsel gösterim için biçimlendirir Biçim belirleyicisi gibidir `"1.729e+01"` . |
| `fixed` | `from_chars()`Bir üs beklenmez veya ayrıştırılamaz. Bu, `printf()` `'f'` gibi kayan nokta biçimlerini belirleyen Biçim belirleyicisi gibidir `"17.29"` .|
| `hex` | `from_chars()`Sayıyı onaltılık biçimde, ancak önünde bir değer olmadan beklemesine neden olur `0x` . |
| `general` | `from_chars()`Bir üs kabul edilmesine (ancak gerektirmez) neden olur. İçin `to_chars()` , `printf()` `'g'` bilimsel gösterim veya sabit arasında geçiş yapmak üzere Biçim belirleyicisi gibidir. Bu, üs 'un ne kadar etkili olacağını göz önünde bulundurarak, bu sayede makul bir küçük çıkış oluşturabilir. Örneğin: `1e-5` içindeki sonuçları `"1e-05"` , ancak `1e-4` Sonuç olarak sonuçlanır `"0.001"` . `1e5` içindeki sonuçlar `100000` , ile sonuçlanır `1e6` `1e+06` . `1e0` üretir `1` .|

## <a name="remarks"></a>Açıklamalar

[From_chars](charconv-functions.md#from_chars) işlevleri için, Bu Enum ne tür bir giriş beklendiğini açıklar.
[To_chars](charconv-functions.md#to_chars) işlevleri için, hangi tür çıktının yayılacağını açıklar.

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<charconv>

**Ad alanı:** std

/std: c++ 17 veya sonraki bir sürümü gereklidir.

## <a name="see-also"></a>Ayrıca bkz.

[\<charconv>](../standard-library/charconv.md)  
[printf () biçim belirticileri](..\c-runtime-library\format-specification-syntax-printf-and-wprintf-functions.md)
