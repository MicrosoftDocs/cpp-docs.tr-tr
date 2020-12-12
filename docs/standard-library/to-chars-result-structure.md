---
description: 'Hakkında daha fazla bilgi edinin: to_chars_result struct'
title: to_chars_result yapısı
ms.date: 07/22/2020
f1_keywords:
- charconv/std::to_chars_result
helpviewer_keywords:
- to_chars_result class
- to_chars_result structure
ms.openlocfilehash: fb043ba928f086549aea326419ec3a2d673723ba
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167194"
---
# <a name="to_chars_result-struct"></a>to_chars_result yapısı

## <a name="syntax"></a>Syntax

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
