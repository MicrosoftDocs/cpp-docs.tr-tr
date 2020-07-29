---
title: OffsetOf makrosu
ms.date: 11/04/2016
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- offsetof
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
ms.openlocfilehash: ee6d5e56bb9f41a842e53984f754c7c07d58a125
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 07/27/2020
ms.locfileid: "87213508"
---
# <a name="offsetof-macro"></a>OffsetOf makrosu

Üyenin üst yapısının başından itibaren konumunu alır.

## <a name="syntax"></a>Söz dizimi

```C
size_t offsetof(
   structName,
   memberName
);
```

### <a name="parameters"></a>Parametreler

*structName*<br/>
Üst veri yapısının adı.

*memberName*<br/>
Kaydırın belirleneceği üst veri yapısındaki üyenin adı.

## <a name="return-value"></a>Dönüş Değeri

**OffsetOf** , üst veri yapısının başlangıcından itibaren belirtilen üyenin bayt cinsinden sapmasını döndürür. Bit alanları için tanımsızdır.

## <a name="remarks"></a>Açıklamalar

**OffsetOf** makrosu, **size_t**türünde bir değer olarak *structName* tarafından belirtilen yapının başlangıcından itibaren, *MemberName* 'in bayt cinsinden sapmasını döndürür. Anahtar sözcüğü ile türleri belirtebilirsiniz **`struct`** .

> [!NOTE]
> **OffsetOf** bir işlev değildir ve bir C prototipi kullanılarak açıklanamaz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**OffsetOf**|\<stddef.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek ayırma](../../c-runtime-library/memory-allocation.md)<br/>
