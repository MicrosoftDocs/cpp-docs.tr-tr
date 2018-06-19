---
title: _mbsnbicmp, _mbsnbicmp_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 15038e42b87a9803312df79eb5d235f1add51669
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405022"
---
# <a name="mbsnbicmp-mbsnbicmpl"></a>_mbsnbicmp, _mbsnbicmp_l

Karşılaştırır **n** bayt iki çok baytlı karakter dizeleri ve durumu yok sayar.

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütme uygulamalarda kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*Sayısı*<br/>
Karşılaştırılacak bayt sayısı.

## <a name="return-value"></a>Dönüş Değeri

Dönüş değeri alt dizeler arasındaki ilişkiyi gösterir.

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* substring değerinden *dize2* substring.|
|0|*Dize1* substring aynı *dize2* substring.|
|> 0|*Dize1* substring büyük *dize2* substring.|

Bir hata **_mbsnbicmp** döndürür **_NLSCMPERROR**, String.h ve Mbstring.h tanımlanmış.

## <a name="remarks"></a>Açıklamalar

**_Mbsnbicmp** işlevi gerçekleştiren bir sıralı karşılaştırma en fazla ilk *sayısı* bayt *Dize1* ve *dize2*. Her karakteri küçük harf dönüştürerek karşılaştırma gerçekleştirilir; [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) büyük küçük harfe duyarlı bir sürümü **_mbsnbicmp**. Karşılaştırma sonlandırma bir null karakter önce ya da dizesinde ulaşıldığında sona *sayısı* karakter karşılaştırılır. Dizeleri eşitse, ne zaman bir sonlandırma null karakter ulaşıldığında önce ya da dizesinde *sayısı* karakter karşılaştırılır, kısa daha düşük bir dizedir.

**_mbsnbicmp** benzer [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md)dizeleri kadar karşılaştırır dışında *sayısı* karaktere göre yerine bayt.

Karakterleri içeren iki dizeyi 'Z' arasında yer alan ve ASCII tablosundaki ' bir' ('[','\\', ']', ' ^', '_' ve '\`') farklı şekilde, kendi çalışması bağlı olarak karşılaştırın. Örneğin, iki "ABCDE" dizeleri ve "ABCD ^" karşılaştırma küçük harf ise bir yolu karşılaştırma ("abcde" > "abcd ^") ve diğer bir yol ("ABCDE" < "ABCD ^") büyük harf ise.

**_mbsnbicmp** göre çok baytlı karakter sıralarının tanıdığı [birden çok baytlı kod sayfası](../../c-runtime-library/code-pages.md) şu anda kullanımda. Geçerli yerel ayarı tarafından etkilenmez.

Her iki *Dize1* veya *dize2* null işaretçi **_mbsnbicmp** açıklandığı gibi geçersiz bir parametre işleyiciyi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, işlevi döndürür **_NLSCMPERROR** ve ayarlar **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsnicmp_l**|**_strnicmp_l**|**_mbsnbicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mbsnbicmp**|< mbstring.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_stricmp, _wcsicmp, _mbsicmp, _stricmp_l, _wcsicmp_l, _mbsicmp_l](stricmp-wcsicmp-mbsicmp-stricmp-l-wcsicmp-l-mbsicmp-l.md)<br/>
