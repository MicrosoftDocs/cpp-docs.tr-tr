---
description: 'Daha fazla bilgi edinin: OffsetOf makrosu'
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
ms.openlocfilehash: 055bda67bae178143561acd91b517c431f77cac0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97256281"
---
# <a name="offsetof-macro"></a>OffsetOf makrosu

Üyenin üst yapısının başından itibaren konumunu alır.

## <a name="syntax"></a>Sözdizimi

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

**OffsetOf** makrosu, **size_t** türünde bir değer olarak *structName* tarafından belirtilen yapının başlangıcından itibaren, *MemberName* 'in bayt cinsinden sapmasını döndürür. Anahtar sözcüğü ile türleri belirtebilirsiniz **`struct`** .

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
