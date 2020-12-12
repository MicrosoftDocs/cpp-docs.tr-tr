---
description: 'Hakkında daha fazla bilgi edinin: _mbsbtype _mbsbtype_l'
title: _mbsbtype, _mbsbtype_l
ms.date: 4/2/2020
api_name:
- _mbsbtype_l
- _mbsbtype
- _o__mbsbtype
- _o__mbsbtype_l
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
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbsbtype
- mbsbtype_l
- _mbsbtype_l
- _mbsbtype
helpviewer_keywords:
- _mbsbtype function
- mbsbtype function
- _mbsbtype_l function
- mbsbtype_l function
ms.assetid: 0d5dd91a-d32d-4f98-ac57-98dfc9e98eac
ms.openlocfilehash: a1d17a947d830281b05291601c74ee944cebdb10
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97271063"
---
# <a name="_mbsbtype-_mbsbtype_l"></a>_mbsbtype, _mbsbtype_l

Bir dize içindeki Byte türünü döndürür.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _mbsbtype(
   const unsigned char *mbstr,
   size_t count
);
int _mbsbtype_l(
   const unsigned char *mbstr,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*mbstr*<br/>
Çok baytlı karakter dizisinin adresi.

*biriktirme*<br/>
Dize kafasının bayt kayması.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_mbsbtype** ve **_mbsbtype_l** , belirtilen bayt üzerindeki testin sonucunu gösteren bir tamsayı değeri döndürür. Aşağıdaki tablodaki bildirim sabitleri Mbctype. h içinde tanımlanmıştır.

|Döndürülen değer|Bayt türü|
|------------------|---------------|
|**_MBC_SINGLE** (0)|Tek baytlık karakter. Örneğin, kod sayfası 932 ' de, belirtilen bayt 0x20-0x7E veya 0xA1 – 0xDF aralığı içindeyse **_mbsbtype** 0 döndürür.|
|**_MBC_LEAD** (1)|Çok baytlı karakterin ön baytı. Örneğin, kod sayfası 932 ' de, belirtilen bayt 0x81-0x9F veya 0xE0-0xFC aralığında olduğunda **_mbsbtype** 1 değerini döndürür.|
|**_MBC_TRAIL** (2)|Çok baytlı karakterin sondaki baytı. Örneğin, kod sayfası 932 ' de, belirtilen bayt 0x40-0x7E veya 0x80 – 0xFC aralığında ise, **_mbsbtype** 2 değerini döndürür.|
|**_MBC_ILLEGAL** (-1)|*Mbstr* içindeki konum *sayısında* bayttan önce **null** dize, geçersiz karakter veya null bayt bulundu.|

## <a name="remarks"></a>Açıklamalar

**_Mbsbtype** işlevi, çok baytlı bir karakter dizesindeki bir baytın türünü belirler. İşlev, belirtilen bayttan önceki geçersiz karakterleri yoksayarak yalnızca *mbstr* içindeki konum *sayısında* bulunan baytı inceler.

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale](setlocale-wsetlocale.md) . Bu işlevin **_l** soneki olmadan sürümü, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; **_l** sonekine sahip sürüm, bunun yerine geçirilen yerel ayar parametresini kullanması dışında aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Giriş dizesi **null** Ise, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlev **_MBC_ILLEGAL** döndürür.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı başlık|
|-------------|---------------------|---------------------|
|**_mbsbtype**|\<mbstring.h>|\<mbctype.h>*|
|**_mbsbtype_l**|\<mbstring.h>|\<mbctype.h>*|

\* Dönüş değeri olarak kullanılan bildirim sabitleri için.

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>Ayrıca bkz.

[Bayt sınıflandırması](../../c-runtime-library/byte-classification.md)<br/>
