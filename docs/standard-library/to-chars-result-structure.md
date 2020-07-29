---
title: to_chars_result yapısı
ms.date: 07/22/2020
f1_keywords:
- charconv/std::to_chars_result
helpviewer_keywords:
- to_chars_result class
- to_chars_result structure
ms.openlocfilehash: a840b8d030f0ed0d2a4afcc57e1bef1161c76ff3
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212067"
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