---
title: _mbbtombc, _mbbtombc_l
ms.date: 11/04/2016
apiname:
- _mbbtombc_l
- _mbbtombc
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
- _mbbtombc_l
- _mbbtombc
- mbbtombc_l
- mbbtombc
helpviewer_keywords:
- mbbtombc_l function
- mbbtombc function
- _mbbtombc_l function
- _mbbtombc function
ms.assetid: 78593389-b0fc-43b6-8c1f-2a6bf702d64e
ms.openlocfilehash: 63b5dd33399201cd6ead7dbd1f710c8bebe53c69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62156914"
---
# <a name="mbbtombc-mbbtombcl"></a>_mbbtombc, _mbbtombc_l

Bir tek baytlık çok baytlı karakteri karşılık gelen bir çift baytlık çok baytlı karaktere dönüştürür.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
unsigned int _mbbtombc(
   unsigned int c
);
unsigned int _mbbtombc_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*c*<br/>
Dönüştürülecek tek baytlı karakter.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Varsa **_mbbtombc** başarıyla dönüştürür *c*, çok baytlı bir karakter döndürür; Aksi halde *c*.

## <a name="remarks"></a>Açıklamalar

**_Mbbtombc** işlevi, karşılık gelen bir çift baytlık çok baytlı karakterin tek baytlık çok baytlı bir karakteri dönüştürür. Karakter 0xDF dönüştürülecek 0x20-0x7E veya 0xA1 - aralığında olması gerekir.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Bu işlevin sürümleri özdeş dışında **_mbbtombc** bu yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır ve **_mbbtombc_l** bunun yerine iletilen yerel ayar parametresini kullanır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Önceki sürümlerde **_mbbtombc** taşıyordu **hantozen**. Yeni kod için kullanmak **_mbbtombc**.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbbtombc**|\<Mbstring.h >|
|**_mbbtombc_l**|\<Mbstring.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_mbctombb, _mbctombb_l](mbctombb-mbctombb-l.md)<br/>
