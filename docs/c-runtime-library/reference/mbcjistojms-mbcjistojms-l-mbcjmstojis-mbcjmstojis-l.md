---
title: _mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l
ms.date: 4/2/2020
api_name:
- _mbcjistojms
- _mbcjmstojis
- _mbcjistojms_l
- _mbcjmstojis_l
- _o__mbcjistojms
- _o__mbcjistojms_l
- _o__mbcjmstojis
- _o__mbcjmstojis_l
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
- mbcjistojms
- _mbcjistojms
- _mbcjistojms_l
- _mbcjmstojis_l
- _mbcjmstojis
- mbcjmstojis_l
- mbcjistojms_l
- mbcjmstojis
helpviewer_keywords:
- _mbcjmstojis_l function
- _mbcjistojms function
- mbcjmstojis function
- _mbcjistojms_l function
- _mbcjmstojis function
- mbcjistojms function
- mbcjmstojis_l function
- mbcjistojms_l function
ms.assetid: dece5127-b337-40a4-aa10-53320a2c9432
ms.openlocfilehash: ef0010088543f1c580e536f120cae681a7582491
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341191"
---
# <a name="_mbcjistojms-_mbcjistojms_l-_mbcjmstojis-_mbcjmstojis_l"></a>_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l

Japonya Endüstri Standardı (JIS) ve Japonya Microsoft (JMS) karakterleri arasında dönüştürme.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _mbcjistojms(
   unsigned int c
);
unsigned int _mbcjistojms_l(
   unsigned int c,
   _locale_t locale
);
unsigned int _mbcjmstojis(
   unsigned int c
);
unsigned int _mbcjmstojis_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*C*<br/>
Karakter dönüştürmek için.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Japonca'da, bu işlevler dönüştürülmüş bir karakter döndürür veya dönüşüm mümkün değilse 0 döndürür. Japonca olmayan bir yerde, bu işlevler geçen karakteri döndürer.

## <a name="remarks"></a>Açıklamalar

**_mbcjistojms** işlevi, Japonya Endüstri Standardı (JIS) karakterini Microsoft Kanji (Shift JIS) karakterine dönüştürür. Karakter yalnızca kurşun ve iz baytları 0x21 - 0x7E aralığındaysa dönüştürülür. Müşteri adayı veya deneme baytbu aralığının dışındaysa, **errno** **EILSEQ**olarak ayarlanır. Bu ve diğer hata kodları hakkında daha fazla bilgi için [bkz: errno, _doserrno, _sys_errlist ve _sys_nerr.](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)

_mbcjmstojis **_mbcjmstojis** işlevi Shift JIS karakterini JIS karakterine dönüştürür. Karakter yalnızca kurşun bayt 0x81 - 0x9F veya 0xE0 - 0xE0 aralığında ysa ve iz bayt 0x40 - 0x7E veya 0x80 - 0xFC aralığında ise dönüştürülür. Bu aralıktaki bazı kod noktalarının atanmış bir karaktere sahip olmadığını ve bu nedenle dönüştürülemeyeceğini unutmayın.

*C* değeri, üst 8 biti dönüştürülecek karakterin kurşun baytını temsil eden ve alt 8 biti iz baytını temsil eden 16 bitlik bir değer olmalıdır.

Çıktı değeri, yerel LC_CTYPE **kategori** ayarı ayarı etkilenir; daha fazla bilgi için [setlocale'ye](setlocale-wsetlocale.md) bakın. Bu işlevlerin **_l** soneki olmayan sürümleri, bu yerele bağımlı davranış için geçerli yerel durumu kullanır; **_l** soneki olan sürümler, bunun yerine geçirilen yerel parametreyi kullanmaları dışında aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Daha önceki **versiyonlarda, _mbcjistojms** ve **_mbcjmstojis** **sırasıyla jistojms** ve **jmstojis**olarak adlandırılıyordu. **bunun**yerine _mbcjistojms , **_mbcjistojms_l,** **_mbcjmstojis** ve **_mbcjmstojis_l** kullanılmalıdır.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbcjistojms**|\<mbstring.h>|
|**_mbcjistojms_l**|\<mbstring.h>|
|**_mbcjmstojis**|\<mbstring.h>|
|**_mbcjmstojis_l**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_ismbb Rutinleri](../../c-runtime-library/ismbb-routines.md)<br/>
