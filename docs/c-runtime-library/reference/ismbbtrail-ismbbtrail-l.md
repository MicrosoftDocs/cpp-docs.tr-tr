---
title: _ismbbtrail, _ismbbtrail_l
ms.date: 4/2/2020
api_name:
- _ismbbtrail
- _ismbbtrail_l
- _o__ismbbtrail
- _o__ismbbtrail_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _ismbbtrail
- ismbbtrail
- _ismbbtrail_l
- ismbbtrail_l
helpviewer_keywords:
- ismbbtrail_l function
- _ismbbtrail function
- _ismbbtrail_l function
- ismbbtrail function
ms.assetid: dfdd0292-960b-4c1d-bf11-146e0fc80247
ms.openlocfilehash: 5e8615adf5d17986c1a52658fe5d680cc326976a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343396"
---
# <a name="_ismbbtrail-_ismbbtrail_l"></a>_ismbbtrail, _ismbbtrail_l

Baytın çok bayt karakterli bir bayt olup olmadığını belirler.

## <a name="syntax"></a>Sözdizimi

```C
int _ismbbtrail(
   unsigned int c
);
int _ismbbtrail_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Test edilecek bir sonda.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_ismbbtrail,** tamsayı *c* çok bayt karakterin ikinci baytıysa sıfır olmayan bir değer verir. Örneğin, yalnızca kod sayfası 932'de geçerli aralıklar 0x40 - 0x7E ve 0x80 -0xFC'dir.

## <a name="remarks"></a>Açıklamalar

**_ismbbtrail,** yerele bağımlı davranış için geçerli yerel alanı kullanır. **_ismbbtrail_l,** bunun yerine geçen yerel alanı kullanması dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|
|-------------|---------------------|---------------------|
|**_ismbbtrail**|\<mbctype.h> \<veya mbstring.h>|\<ctype.h>,* \<limits.h \<>, stdlib.h>|
|**_ismbbtrail_l**|\<mbctype.h> \<veya mbstring.h>|\<ctype.h>,* \<limits.h \<>, stdlib.h>|

\*Test koşulları için manifesto sabitleri için.

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Bayt Sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb Rutinleri](../../c-runtime-library/ismbb-routines.md)<br/>
