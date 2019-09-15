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
ms.openlocfilehash: 278fca89046fcfc98e8c3ff726918cb4319e4ab0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70951256"
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

**OffsetOf** makrosu,, *structName* tarafından belirtilen yapının başlangıcından itibaren, **size_t**türünde bir değer olarak, *MemberName* 'in bayt cinsinden sapmasını döndürür. **Struct** anahtar sözcüğünü içeren türler belirtebilirsiniz.

> [!NOTE]
> **OffsetOf** bir işlev değildir ve bir C prototipi kullanılarak açıklanamaz.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**OffsetOf**|\<stddef. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Kitaplıklar

[C çalışma zamanı kitaplıklarının](../../c-runtime-library/crt-library-features.md)tüm sürümleri.

## <a name="see-also"></a>Ayrıca bkz.

[Bellek Ayırma](../../c-runtime-library/memory-allocation.md)<br/>
