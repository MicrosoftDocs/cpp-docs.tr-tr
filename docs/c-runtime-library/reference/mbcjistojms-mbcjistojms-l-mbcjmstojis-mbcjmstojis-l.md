---
title: _mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l
ms.date: 11/04/2016
api_name:
- _mbcjistojms
- _mbcjmstojis
- _mbcjistojms_l
- _mbcjmstojis_l
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
ms.openlocfilehash: 6bf1109cfba93042bd00acde4812706c1bbf7a01
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952597"
---
# <a name="_mbcjistojms-_mbcjistojms_l-_mbcjmstojis-_mbcjmstojis_l"></a>_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l

Japonya endüstri standardı (JıS) ve Japonya Microsoft (JMS) karakterleri arasında dönüştürür.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*c*<br/>
Dönüştürülecek karakter.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Japonca yerel ayarında, bu işlevler dönüştürülmüş bir karakter döndürür veya dönüştürme mümkün değilse 0 döndürür. Japonca olmayan bir yerel ayarda, bu işlevler geçirilen karakteri döndürür.

## <a name="remarks"></a>Açıklamalar

**_Mbcjistojms** işlevi, bir Japonya endüstri standardı (JIS) karakterini Microsoft Kanji (Shift JIS) karakterine dönüştürür. Karakter yalnızca, öncü ve sondaki baytlar 0x21-0x7E aralığında olduğunda dönüştürülür. Lider veya deneme baytı bu aralığın dışındaysa, **errno** **eilseq**olarak ayarlanır. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [errno, _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**_Mbcjmstojıs** Işlevi BIR Shift JıS karakterini JIS karaktere dönüştürür. Karakter yalnızca, ön bayt 0x81-0x9F veya 0xE0-0xFC aralığında ise ve iz baytı 0x40-0x7E veya 0x80-0xFC aralığında olduğunda dönüştürülür. Bu aralıktaki bazı kod noktalarında atanmış bir karakter olmadığı ve dönüştürülemediği unutulmamalıdır.

*C* değeri, üst 8 bit, dönüştürülecek karakterin baş baytını temsil eden ve daha düşük 8 bit, iz baytı temsil eden 16 bitlik bir değer olmalıdır.

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md) . **_L** sonekine sahip olmayan bu işlevlerin sürümleri, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip sürümler, bunun yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Önceki sürümlerde, **_mbcjistojms** ve **_mbcjmstojıs** sırasıyla **jistojms** ve **jmstojıs**olarak adlandırılmıştı. **_mbcjistojms**, **_mbcjistojms_l**, **_mbcjmstojıs** ve **_mbcjmstojis_l** bunun yerine kullanılmalıdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbcjistojms**|\<mbstring. h >|
|**_mbcjistojms_l**|\<mbstring. h >|
|**_mbcjmstojis**|\<mbstring. h >|
|**_mbcjmstojis_l**|\<mbstring. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
