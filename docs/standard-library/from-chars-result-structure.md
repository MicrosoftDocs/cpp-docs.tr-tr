---
title: from_chars_result yapısı
ms.date: 7/23/2020
f1_keywords:
- std::from_chars_result
helpviewer_keywords:
- from_chars_result class
- from_chars_result structure
ms.openlocfilehash: 5a5dcfe6e5b59644e6ebf55d68ce43975e7d3c9d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87215770"
---
# <a name="from_chars_result-struct"></a>from_chars_result yapısı

## <a name="syntax"></a>Sözdizimi

```cpp
struct from_chars_result {
    const char* ptr;
    errc ec;
};
```

|Üye|Açıklama|
|--|--|
|`ptr`| `ec`Şuna eşitse `errc{}` , dönüştürme başarılı olur ve `ptr` tanınan sayının parçası olmayan ilk karakteri işaret eder. |
|`ec` | Dönüştürme hata kodu. Belirli hata kodları için bkz [`errc`](system-error-enums.md#errc) ..|

### <a name="remarks"></a>Açıklamalar

Örnek: bir `"1729cats"` ondalık tamsayı olarak ayrıştırma başarılı olur ve `ptr` `'c'` ilk basamak dışı ve aynı zamanda bir-son sonu olan ' i işaret eder `"1729"` .

Bir sayı düzeniyle eşleşen bir karakter yoksa, `from_chars_result.ptr` `first` ve ' a işaret `from_chars_result.ec` eder `errc::invalid_argument` .

Bir sayı düzeniyle yalnızca bazı karakterler eşleşirse, bu, `from_chars_result.ptr` Düzenle eşleşmeyen ilk karaktere işaret eder veya `last` tüm karakterler eşleşiyorsa parametre değeri vardır.

Ayrıştırılmış değer, yapılan dönüştürme türü için aralığa uymuyorsa, `from_chars_result.ec` olur `errc::result_out_of_range` .

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<charconv>

**Ad alanı:** std

**Derleyici seçeneği:** /std: c++ 17 veya üzeri, gereklidir

## <a name="see-also"></a>Ayrıca bkz.

[from_chars](charconv-functions.md#from_chars)
