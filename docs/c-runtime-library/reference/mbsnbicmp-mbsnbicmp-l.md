---
title: _mbsnbicmp, _mbsnbicmp_l
ms.date: 11/04/2016
apiname:
- _mbsnbicmp_l
- _mbsnbicmp
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
- _strnicmp
- _wcsnicmp_l
- _mbsnbicmp
- mbsnbicmp
- mbsnbicmp_l
- _tcsnicmp
- _strnicmp_l
- _tcsnicmp_l
- _wcsnicmp
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
ms.openlocfilehash: 059d0781e465f6491f27fd634bbc4479104bc12f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62331304"
---
# <a name="mbsnbicmp-mbsnbicmpl"></a>_mbsnbicmp, _mbsnbicmp_l

Karşılaştırır **n** iki çok baytlı karakterinin bayt dizeleri ve çalışması yok sayar.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Karşılaştırmak için null ile sonlandırılmış dizeler.

*Sayısı*<br/>
Karşılaştırılacak bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri alt dizeler arasındaki ilişkiyi gösterir.

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* alt dize küçüktür *dize2* alt dize.|
|0|*Dize1* aynı alt dizeyi *dize2* alt dize.|
|> 0|*Dize1* alt dizeyi büyük *dize2* alt dize.|

Bir hatada **_mbsnbicmp** döndürür **_NLSCMPERROR**, String.h ve Mbstring.h içinde tanımlanan.

## <a name="remarks"></a>Açıklamalar

**_Mbsnbicmp** işlevi, en fazla ilk sıralı bir karşılaştırma gerçekleştirir *sayısı* bayt *Dize1* ve *dize2*. Her bir karakteri küçük harfe dönüştürerek bir karşılaştırma gerçekleştirilir; [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) büyük küçük harfe duyarlı bir sürümüdür **_mbsnbicmp**. Bir sonlandırıcı null karakter ya da dize önce ulaşılırsa karşılaştırma sonlandırır *sayısı* karakter karşılaştırılmadan. Dizeler eşitse bir sonlandırıcı null karakter ulaşıldığında önce her iki dizede *sayısı* karakter karşılaştırılmadan, kısa dize küçüktür.

**_mbsnbicmp** benzer [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md)kadar dizeleri karşılaştırır, dışında *sayısı* karakter yerine bayt.

'Z' arasında karakterler içeren iki dize bulunan ve ASCII tablosunda ' bir' ('[','\\', ']', ' ^', '_' ve '\`') bağlı olarak farklı şekilde karşılaştırın. Örneğin, iki "ABCDE" dizeleri ve "ABCD ^" karşılaştırma küçük harf ise tek yolla karşılaştırılır ("abcde" > "abcd ^") ve başka bir yolla ("ABCDE" < "ABCD ^") büyük harf ise.

**_mbsnbicmp** çok baytlı karakter sıralarına göre tanır [çok baytlı kod sayfası](../../c-runtime-library/code-pages.md) şu anda kullanımda. Geçerli yerel ayar tarafından etkilenmez.

Ya da *Dize1* veya *dize2* null bir işaretçiyse, **_mbsnbicmp** açıklandığı gibi geçersiz parametre işleyicisi çağırır [parametredoğrulama](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, işlev döndürür **_NLSCMPERROR** ve ayarlar **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsnicmp_l**|**_strnicmp_l**|**_mbsnbicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbicmp**|\<Mbstring.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
