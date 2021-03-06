---
description: 'Hakkında daha fazla bilgi edinin: from_chars_result struct'
title: from_chars_result yapısı
ms.date: 7/23/2020
f1_keywords:
- std::from_chars_result
helpviewer_keywords:
- from_chars_result class
- from_chars_result structure
ms.openlocfilehash: 894a687a4395e22538b384675af5b4ce57731f78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97232284"
---
# <a name="from_chars_result-struct"></a>from_chars_result yapısı

## <a name="syntax"></a>Syntax

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
