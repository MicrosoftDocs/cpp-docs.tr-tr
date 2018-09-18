---
title: _strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wcsnicmp
- _strnicmp_l
- _wcsnicmp_l
- _strnicmp
- _mbsnicmp
- _mbsnicmp_l
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- wcsnicmp_l
- _strnicmp
- _ftcsnicmp
- mbsnicmp_l
- _ftcsncicmp
- mbsnicmp
- _tcsncicmp
- _mbsnicmp
- _tcsnicmp
- strnicmp_l
- _wcsnicmp
- _wcsnicmp_l
- CORECRT_WSTRING/_wcsnicmp
- CORECRT_WSTRING/_wcsnicmp_l
- string/_strnicmp
- string/_strnicmp_l
dev_langs:
- C++
helpviewer_keywords:
- tcsnicmp function
- _tcsncicmp function
- _mbsnicmp_l function
- mbsnicmp_l function
- wcsnicmp_l function
- wcsnicmp function
- string comparison [C++], lowercase
- ftcsnicmp function
- strnicmp_l function
- strncmp function
- _strnicmp function
- strings [C++], comparing characters of
- _wcsnicmp_l function
- tcsncicmp function
- string comparison [C++], strncmp function
- _mbsnicmp function
- ftcsncicmp function
- _tcsnicmp function
- _ftcsncicmp function
- _strnicmp_l function
- _ftcsnicmp function
- characters [C++], comparing
- mbsnicmp function
- _wcsnicmp function
ms.assetid: df6e5037-4039-4c85-a0a6-21d4ef513966
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a06bbfb66030a8f037ce83323486d10107bf505
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020322"
---
# <a name="strnicmp-wcsnicmp-mbsnicmp-strnicmpl-wcsnicmpl-mbsnicmpl"></a>_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l

Belirtilen sayıda karakteri çalışması dikkate almaksızın, iki dizenin karşılaştırır.

> [!IMPORTANT]
> **_mbsnicmp** ve **_mbsnicmp_l** Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _strnicmp(
   const char *string1,
   const char *string2,
   size_t count
);
int _wcsnicmp(
   const wchar_t *string1,
   const wchar_t *string2,
   size_t count
);
int _mbsnicmp(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _strnicmp_l(
   const char *string1,
   const char *string2,
   size_t count,
   _locale_t locale
);
int _wcsnicmp_l(
   const wchar_t *string1,
   const wchar_t *string2,
   size_t count,
   _locale_t locale
);
int _mbsnicmp_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*Dize1*, *dize2*<br/>
Karşılaştırmak için null ile sonlandırılmış dizeler.

*Sayısı*<br/>
Karşılaştırılacak karakter sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Aşağıdaki gibi alt dizeler arasındaki ilişkiyi gösterir.

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* alt dizesidir küçüktür *dize2* alt dize.|
|0|*Dize1* substring aynıdır *dize2* alt dize.|
|> 0|*Dize1* alt dizeyi büyük *dize2* alt dize.|

Bu işlevler bir parametre doğrulama hatasını döndürür **_NLSCMPERROR**, tanımlanan \<string.h > ve \<mbstring.h >.

## <a name="remarks"></a>Açıklamalar

**_Strnicmp** işlevi ordinally karşılaştırır, en çok ilk *sayısı* karakterlerinden *Dize1* ve *dize2*. Karşılaştırma çalışması bakılmaksızın, her bir karakteri küçük harfe dönüştürme tarafından gerçekleştirilir. **_strnicmp** büyük küçük harf duyarlı bir sürümüdür **strncmp**. Bir sonlandırıcı null karakter ya da dize önce ulaşılırsa karşılaştırma sonlandırır *sayısı* karakter karşılaştırılmadan. Dizeler eşitse bir sonlandırıcı null karakter ulaşıldığında önce her iki dizede *sayısı* karakter karşılaştırılmadan, kısa dize küçüktür.

ASCII tablosunda 96 91 karakterleri ('[','\\', ']', ' ^', '_' ve '\`') olarak küçüktür herhangi bir alfabetik karakterle değerlendirin. Bu sıralama olarak aynı **stricmp**.

**_wcsnicmp** ve **_mbsnicmp** geniş karakter ve çok baytlı karakter sürümleridir **_strnicmp**. Bağımsız değişkenleri **_wcsnicmp** geniş karakterli dizelerdir; **_mbsnicmp** çok baytlı karakter dizeleridir. **_mbsnicmp** geçerli çok baytlı kod sayfasına göre çok baytlı karakter dizileri tanır ve döndürür **_NLSCMPERROR** üzerinde hata. Daha fazla bilgi için [kod sayfaları](../../c-runtime-library/code-pages.md). Bu üç işlev aynı şekilde davranır. Bu işlevler, yerel ayar tarafından etkilenen — sahip olmayan sürümleri **_l** soneki geçerli yerel ayar için yerel ayara bağlı davranışları; sahip sürümler **_l** soneki Bunun yerine kullanın *yerel ayar* olarak geçirilir. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Bu işlevlerin tümü kendi parametrelerini doğrular. Ya da *Dize1* veya *dize2* null bir işaretçiyse, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **_NLSCMPERROR** ayarlayıp **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsncicmp**|**_strnicmp**|**_mbsnicmp**|**_wcsnicmp**|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsncicmp_l**|**_strnicmp_l**|**_mbsnicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strnicmp**, **_strnicmp_l**|\<String.h >|
|**_wcsnicmp**, **_wcsnicmp_l**|\<String.h > veya \<wchar.h >|
|**_mbsnicmp**, **_mbsnicmp_l**|\<Mbstring.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bakın [strncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md).

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
