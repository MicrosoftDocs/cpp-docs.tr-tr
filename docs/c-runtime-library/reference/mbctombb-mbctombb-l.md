---
title: _mbctombb, _mbctombb_l
ms.date: 11/04/2016
apiname:
- _mbctombb_l
- _mbctombb
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
- _mbctombb_l
- _mbctombb
- mbctombb_l
- mbctombb
helpviewer_keywords:
- _mbctombb function
- mbctombb_l function
- mbctombb function
- _mbctombb_l function
ms.assetid: d90970b8-71ff-4586-b6a2-f9ceb811f776
ms.openlocfilehash: 7395d94a6ec18f989d4a7153425b7af406a0bf45
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519840"
---
# <a name="mbctombb-mbctombbl"></a>_mbctombb, _mbctombb_l

Çift baytlık çok baytlı bir karakterin ilgili tek baytlık çok baytlı karaktere dönüştürür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _mbctombb(
   unsigned int c
);
unsigned int _mbctombb_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Dönüştürülecek çok baytlı karakter.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa, **_mbctombb** ve **_mbctombb_l** karşılık gelen tek baytlık karakteri döndürür *c*; Aksi halde döndürür *c* .

## <a name="remarks"></a>Açıklamalar

**_Mbctombb** ve **_mbctombb_l** işlevleri karşılık gelen bir tek baytlık çok baytlı karakterin çok baytlı bir karakteri dönüştürür. Karakterler tek baytlık karakter 0x20-0x7E veya 0xA1 - aralık içinde dönüştürülecek 0xDF karşılık gelmelidir.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevin sürümünü **_l** soneki, bu yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır sürümüyle **_l** soneki, onu kullanmalarıdır iletilmiş yerel ayar parametresini aynıdır Bunun yerine. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Önceki sürümlerde, **_mbctombb** çağrıldı **zentohan**. Kullanım **_mbctombb** yerine.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbctombb**|\<Mbstring.h >|
|**_mbctombb_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_mbbtombc, _mbbtombc_l](mbbtombc-mbbtombc-l.md)<br/>
[_mbcjistojms, _mbcjistojms_l, _mbcjmstojis, _mbcjmstojis_l](mbcjistojms-mbcjistojms-l-mbcjmstojis-mbcjmstojis-l.md)<br/>
[_mbctohira, _mbctohira_l, _mbctokata, _mbctokata_l](mbctohira-mbctohira-l-mbctokata-mbctokata-l.md)<br/>
[_mbctolower, _mbctolower_l, _mbctoupper, _mbctoupper_l](mbctolower-mbctolower-l-mbctoupper-mbctoupper-l.md)<br/>
