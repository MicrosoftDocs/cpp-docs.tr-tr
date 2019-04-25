---
title: _mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l
ms.date: 11/04/2016
apiname:
- _mbcjistojms
- _mbcjmstojis
- _mbcjistojms_l
- _mbcjmstojis_l
apilocation:
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
apitype: DLLExport
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
ms.openlocfilehash: 22cf8eeb5f99b6abee624aa3b1d06246d7230652
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156830"
---
# <a name="mbcjistojms-mbcjistojmsl-mbcjmstojis-mbcjmstojisl"></a>_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l

Japon endüstri standardı (JIS) ve Japonya Microsoft (JMS) karakterleri arasında dönüştürür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Japonca yerel ayarında, bu işlevler dönüştürülmüş karakteri veya dönüştürme mümkün değilse 0 değerini döndürür. Japonca dışındaki yerel ayarlarda, bu işlevler geçirilen karakteri döndürür.

## <a name="remarks"></a>Açıklamalar

**_Mbcjistojms** işlevi bir Japon endüstri standardı (JIS) karakterini bir Microsoft Kanji (Shift JIS) karakterine dönüştürür. Karakter yalnızca ön ve arka baytlar 0x21 - 0x7E aralığında ise dönüştürülür. Ön veya deneme baytı bu aralığın dışında kalırsa **errno** ayarlanır **EILSEQ**. Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz. [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

**_Mbcjmstojis** işlevi bir Shift JIS karakterini bir JIS karakterine dönüştürür. Karakter yalnızca ön bayt 0x81-0x9F veya 0xE0 - aralığında 0xfc aralığında olan ve bayt 0x40-0x7E veya 0x80 – 0xfc aralığında menzil dönüştürülür. Bazı kodlar bu aralıktaki atanmış karakter içeren ve dönüştürülemediğini gösterdiğini unutmayın.

Değer *c* , üst 8 biti dönüştürülecek karakterin ön baytını temsil eden ve bayt olan alt 8 bit temsil eden 16-bit bir değer olmalıdır.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevlerin sürümleri **_l** soneki geçerli yerel ayarı kullanır bu yerel ayara bağlı davranışı için; sürümleriyle **_l** sonekine bunların yerel ayar parametresini kullanmalarıdır Bunun yerine iletilmiş. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Önceki sürümlerde **_mbcjistojms** ve **_mbcjmstojis** çağrılan **jistojms** ve **jmstojis**sırasıyla. **_mbcjistojms**, **_mbcjistojms_l**, **_mbcjmstojis** ve **_mbcjmstojis_l** bunun yerine kullanılmalıdır.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbcjistojms**|\<Mbstring.h >|
|**_mbcjistojms_l**|\<Mbstring.h >|
|**_mbcjmstojis**|\<Mbstring.h >|
|**_mbcjmstojis_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_ismbb Yordamları](../../c-runtime-library/ismbb-routines.md)<br/>
