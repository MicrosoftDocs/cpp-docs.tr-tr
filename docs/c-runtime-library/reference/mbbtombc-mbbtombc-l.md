---
title: _mbbtombc, _mbbtombc_l
ms.date: 11/04/2016
api_name:
- _mbbtombc_l
- _mbbtombc
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
ms.openlocfilehash: 244e603a3234b755d19a1c1d0738e8c22d74b8e2
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70952730"
---
# <a name="_mbbtombc-_mbbtombc_l"></a>_mbbtombc, _mbbtombc_l

Tek baytlık çok baytlı bir karakteri karşılık gelen çift baytlık çok baytlı karaktere dönüştürür.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Dönüştürülecek tek baytlık karakter.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_Mbbkaldırıldı c** başarıyla *c*'yi dönüştürdükten sonra çok baytlı bir karakter döndürür; Aksi takdirde, *c*döndürür.

## <a name="remarks"></a>Açıklamalar

**_Mbbkaldırıldı c** işlevi, verilen bir tek baytlık çok baytlı karakteri karşılık gelen çift baytlık çok baytlı karaktere dönüştürür. Karakterler, dönüştürülecek 0x20-0x7E veya 0xA1-0xDF aralığı içinde olmalıdır.

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md) . Bu işlevin sürümleri aynıdır, ancak bu yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır ve bunun yerine **_mbbkaldırıldı c_l** , geçirilen yerel ayar **parametresini kullanır.** Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Önceki sürümlerde, **_mbbkaldırıldı c** , **hantozen**olarak adlandırılmıştır. Yeni kod için **_mbbkaldırıldı c**kullanın.

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbbtombc**|\<mbstring. h >|
|**_mbbtombc_l**|\<mbstring. h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_mbctombb, _mbctombb_l](mbctombb-mbctombb-l.md)<br/>
