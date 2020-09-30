---
title: to_chars_result yapısı
ms.date: 07/22/2020
f1_keywords:
- charconv/std::to_chars_result
helpviewer_keywords:
- to_chars_result class
- to_chars_result structure
ms.openlocfilehash: 4e46d1cc9d0b6a02d731ad25c2e85c99300d7234
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509652"
---
# <a name="to_chars_result-struct"></a>to_chars_result yapısı

## <a name="syntax"></a>Sözdizimi

```cpp
struct to_chars_result {
    char* ptr;
    errc ec;
};
```

## <a name="members"></a>Üyeler

|Üye|Açıklama|
|--|--|
|`ptr`| `ec`Şuna eşitse `errc{}` , dönüştürme başarılı olur ve `ptr` yazılan karakterlerin son bitiş işaretçisidir. Aksi takdirde, `ptr` `to_chars()` parametresinin değeri `last` ve \[ ilk olarak aralığın içeriği belirtilmemiş.|
|`ec` | Dönüştürme hata kodu. Belirli hata kodları için bkz [`errc`](system-error-enums.md#errc) ..|

## <a name="requirements"></a>Gereksinimler

**Üst bilgi:**\<charconv>

**Ad alanı:** std

**Derleyici seçeneği:** /std: c++ 17 veya üzeri, gereklidir

## <a name="see-also"></a>Ayrıca bkz.

[to_chars](charconv-functions.md#to_chars)
