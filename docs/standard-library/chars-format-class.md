---
title: chars_format numaralandırması
ms.date: 07/22/2020
f1_keywords:
- charconv/std::chars_format
helpviewer_keywords:
- std::chars_format
ms.openlocfilehash: 4c1d495c943be02b66d52d1986a783b29a8009c5
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87230188"
---
# <a name="chars_format-enum"></a>chars_format numaralandırması

[\<charconv>](charconv.md)Basit sayısal dönüşümler için kayan nokta biçimini belirtmek üzere kitaplığıyla birlikte kullanılır.

## <a name="syntax"></a>Sözdizimi

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
| `scientific` | `from_chars()`Bir üs beklenmesine ve ayrıştırmasına neden olur. Şöyle gösterimi gibi, `'e'` `printf()` bilimsel gösterim için Biçim belirleyicisi gibidir.`"1.729e+01"` |
| `fixed` | `from_chars()`Bir üs beklenmez veya ayrıştırılamaz. Bu, gibi `'f'` `printf()` kayan nokta biçimlerini belirleyen Biçim belirleyicisi gibidir `"17.29"` .|
| `hex` | `from_chars()`Önünde "0x" olmadan, onaltılık biçimde sayı beklenmesine neden olur. |
| `general` | `from_chars()`Bir üs kabul edilmesine (ancak gerektirmez) neden olur. İçin `to_chars()` , `g` bilimsel gösterim veya sabit arasında geçiş yapmak için printf () Biçim belirleyicisi gibidir. Bu, üs 'un ne kadar etkili olacağını göz önünde bulundurarak, bu sayede makul bir küçük çıkış oluşturabilir. Örneğin: `1e-5` içindeki sonuçları `"1e-05"` , ancak `1e-4` Sonuç olarak sonuçlanır `"0.001"` . `1e5`içindeki sonuçlar `100000` , ile sonuçlanır `1e6` `1e+06` . `1e0`üretir `1` .|

## <a name="remarks"></a>Açıklamalar

[From_chars](charconv-functions.md#from_chars) işlevleri için, Bu Enum ne tür bir giriş beklendiğini açıklar.
[To_chars](charconv-functions.md#to_chars) işlevleri için, hangi tür çıktının yayılacağını açıklar.

## <a name="see-also"></a>Ayrıca bkz.

[\<charconv>](../standard-library/charconv.md)  
[printf () biçim belirticileri](..\c-runtime-library\format-specification-syntax-printf-and-wprintf-functions.md)
