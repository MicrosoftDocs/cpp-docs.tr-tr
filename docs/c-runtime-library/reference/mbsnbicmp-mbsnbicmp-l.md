---
title: _mbsnbicmp, _mbsnbicmp_l
ms.date: 4/2/2020
api_name:
- _mbsnbicmp_l
- _mbsnbicmp
- _o__mbsnbicmp
- _o__mbsnbicmp_l
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
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _mbsnbicmp_l
helpviewer_keywords:
- _tcsnicmp_l function
- _strnicmp function
- mbsnbicmp_l function
- _wcsnicmp_l function
- _mbsnbicmp function
- _mbsnbicmp_l function
- _tcsnicmp function
- _strnicmp_l function
- mbsnbicmp function
- _wcsnicmp function
ms.assetid: ddb44974-8b0c-42f0-90d0-56c9350bae0c
ms.openlocfilehash: 80d2708396cdaeb86c25932c3d13129fb318719a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340574"
---
# <a name="_mbsnbicmp-_mbsnbicmp_l"></a>_mbsnbicmp, _mbsnbicmp_l

İki çok bayt karakterli dizeleri **n** bayt karşılaştırır ve büyük/küçük harf yok sayar.

> [!IMPORTANT]
> Bu API, Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

## <a name="syntax"></a>Sözdizimi

```C
int _mbsnbicmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
```

### <a name="parameters"></a>Parametreler

*string1*, *string2*<br/>
Karşılaştırmak için null-sonlandırılan dizeleri.

*Sayısı*<br/>
Karşılaştırılacak bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

İade değeri, alt dizeleri arasındaki ilişkiyi gösterir.

|Döndürülen değer|Açıklama|
|------------------|-----------------|
|< 0|*string1* *string2* substring daha az substring.|
|0|*string1* substring *string2* substring ile aynıdır.|
|> 0|*string1* alt *dizestring2* substring daha büyüktür.|

Bir hata **da, string.h** ve Mbstring.h'de tanımlanan **_NLSCMPERROR**_mbsnbicmp döndürür.

## <a name="remarks"></a>Açıklamalar

**_mbsnbicmp** işlevi *string1* ve *string2'nin*en çok ilk *sayı* baytlarının bir ordinal karşılaştırmasını gerçekleştirir. Karşılaştırma, her bir karakteri küçük harfe dönüştürerek gerçekleştirilir; [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) **_mbsnbicmp**bir büyük/küçük harf duyarlı sürümüdür. *Sayım* karakterleri karşılaştırılmadan önce her iki dizede de sonlandırıcı null karaktere ulaşılırsa karşılaştırma sona erer. *Sayım* karakterleri karşılaştırılmadan önce her iki dizede sonlandırıcı null karaktere ulaşıldığında dizeleri eşitse, kısa dize daha azdır.

**_mbsnbicmp** [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md)benzer , karakterler yerine bayt *saymak* için dizeleri karşılaştırır dışında.

ASCII tablosunda 'Z' ve 'a' arasında yer alan karakterleri içeren iki\\dize ('',,',',',',']', '^', '_', ve '\`') durumlarına bağlı olarak farklı karşılaştırılır. Örneğin, karşılaştırma küçük ("abcde" > "abcd^") ve diğer yol ("ABCDE" < "ABCD^") büyük ise iki dize "ABCDE" ve "ABCD^" bir şekilde karşılaştırın.

**_mbsnbicmp,** şu anda kullanılmakta olan [çok bayt kod sayfasına](../../c-runtime-library/code-pages.md) göre çok bayt karakter dizilerini tanır. Geçerli yerel ayardan etkilenmez.

*String1* veya *string2* null işaretçisi ise, **_mbsnbicmp** [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmedevam etmesine izin verilirse, işlev **_NLSCMPERROR** döndürür ve **EINVAL** **için errno** ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsnicmp_l**|**_strnicmp_l**|**_mbsnbicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbicmp**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md)_mbsnbcmp_l örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
