---
description: 'Hakkında daha fazla bilgi edinin: _mbsnbicmp _mbsnbicmp_l'
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
- api-ms-win-crt-private-l1-1-0.dll
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
ms.openlocfilehash: 9cc833061ceca899af78da4c50610ed101dcd2d1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240279"
---
# <a name="_mbsnbicmp-_mbsnbicmp_l"></a>_mbsnbicmp, _mbsnbicmp_l

İki çok baytlı karakter dizesinin **n** baytını karşılaştırır ve büyük/küçük harf durumunu yoksayar.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _mbsnbicmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
```

### <a name="parameters"></a>Parametreler

*Dize1*, *dize2*<br/>
Karşılaştırılacak null ile sonlandırılmış dizeler.

*biriktirme*<br/>
Karşılaştırılacak bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri, alt dizeler arasındaki ilişkiyi gösterir.

|Döndürülen değer|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* substring, *dize2* alt dizesi ile küçüktür.|
|0|*Dize1* substring, *dize2* alt dizesi ile özdeş.|
|> 0|*Dize1* substring, *dize2* alt dizinden büyük.|

Bir hatada, **_Mbsnbicmp** String. h ve mbstring. h içinde tanımlanan **_NLSCMPERROR** döndürür.

## <a name="remarks"></a>Açıklamalar

**_Mbsnbicmp** işlevi, *Dize1* ve *dize2*' nin en fazla ilk *sayım* baytından sıralı bir karşılaştırma gerçekleştirir. Karşılaştırma, her karakteri küçük harfe dönüştürerek gerçekleştirilir; [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) , **_mbsnbicmp**, büyük/küçük harfe duyarlı bir sürümdür. *Sayma* karakterleri karşılaştırılmadan önce her iki dizede de bir Sonlandırıcı null karakterine ulaşıldığında karşılaştırma biter. *Sayı* karakterleri karşılaştırılmadan önce bir dizede bir Sonlandırıcı null karakterine ulaşıldığında dizeler eşitse, daha kısa dize daha küçüktür.

**_mbsnbicmp** [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md)benzerdir, ancak dizeleri karakter yerine bayt *sayısı* kadar karşılaştırır.

ASCII tablosunda (' [', ' \\ ', '] ', ' ^ ', ' _ ' ve ' ') ' Z ' ve ' a ' arasında karakter içeren iki dize, \` durumlarına bağlı olarak farklı şekilde karşılaştırın. Örneğin, "ABCDE" ve "ABCD ^" iki dizesi, karşılaştırma küçük harfli ("ABCDE" > "abcd ^") ve diğer yolla ("ABCDE" < "abcd ^") büyük harfli bir şekilde karşılaştırın.

**_mbsnbicmp** , kullanımda olan [çok baytlı kod sayfasına](../../c-runtime-library/code-pages.md) göre çok baytlı karakter dizilerini tanır. Geçerli yerel ayar ayarından etkilenmez.

*Dize1* veya *dize2* , null Işaretçisiyse, **_mbsnbicmp** [parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa işlev **_NLSCMPERROR** döndürür ve **errno** ' ı **EINVAL** olarak ayarlar.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsnicmp_l**|**_strnicmp_l**|**_mbsnbicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbicmp**|\<mbstring.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[_Mbsnbcmp _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
