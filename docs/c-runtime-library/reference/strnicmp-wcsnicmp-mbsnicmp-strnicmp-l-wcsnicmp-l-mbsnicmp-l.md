---
title: _strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l
ms.date: 4/2/2020
api_name:
- _wcsnicmp
- _strnicmp_l
- _wcsnicmp_l
- _strnicmp
- _mbsnicmp
- _mbsnicmp_l
- _o__mbsnicmp
- _o__mbsnicmp_l
- _o__strnicmp
- _o__strnicmp_l
- _o__wcsnicmp
- _o__wcsnicmp_l
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
- api-ms-win-crt-string-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: b0bde60a230f1fd428716073471cd85b2728a614
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364836"
---
# <a name="_strnicmp-_wcsnicmp-_mbsnicmp-_strnicmp_l-_wcsnicmp_l-_mbsnicmp_l"></a>_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l

Büyük/küçük harfe bakılmaksızın iki dizekarakter belirtilen sayısını karşılaştırır.

> [!IMPORTANT]
> **_mbsnicmp** ve **_mbsnicmp_l,** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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

*string1*, *string2*<br/>
Karşılaştırmak için null-sonlandırılan dizeleri.

*Sayısı*<br/>
Karşılaştırılacak karakter sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Aşağıdaki gibi alt dizeleri arasındaki ilişkiyi gösterir.

|Döndürülen değer|Açıklama|
|------------------|-----------------|
|< 0|*string1* substring *string2* substring daha azdır.|
|0|*string1* substring *string2* substring ile aynıdır.|
|> 0|*string1* substring *string2* substring'den büyüktür.|

Parametre doğrulama hatasında, bu **_NLSCMPERROR**işlevler \<string.h> ve \<mbstring.h> tanımlanan _NLSCMPERROR döndürer.

## <a name="remarks"></a>Açıklamalar

**_strnicmp** işlevi, *string1* ve *string2'nin*ilk *sayma* karakterlerini en fazla olarak, ordinally karşılaştırır. Karşılaştırma, her bir karakteri küçük harfe dönüştürerek büyük/küçük harfe bakılmaksızın gerçekleştirilir. **_strnicmp** **strncmp**bir durumda duyarsız sürümüdür. *Sayım* karakterleri karşılaştırılmadan önce her iki dizede de sonlandırıcı null karaktere ulaşılırsa karşılaştırma sona erer. *Sayım* karakterleri karşılaştırılmadan önce her iki dizede sonlandırıcı null karaktere ulaşıldığında dizeleri eşitse, kısa dize daha azdır.

ASCII tablosundaki 91 ile 96 arası karakterler ('[', ' ',',',',',^',\\'_'ve '\`') herhangi bir alfabetik karakterden daha az olarak değerlendirilir. Bu sıralama **stricmp**ile aynıdır.

**_wcsnicmp** ve **_mbsnicmp** **_strnicmp**geniş karakterli ve çok bayt karakterli versiyonlarıdır. **_wcsnicmp** bağımsız değişkenleri geniş karakterli dizeleri vardır; **_mbsnicmp** çok bayt karakterli dizeleri vardır. **_mbsnicmp,** geçerli çok bayt kod sayfasına göre çok bayt karakter dizilerini tanır ve bir hata üzerinde **_NLSCMPERROR** döndürür. Daha fazla bilgi için [Kod Sayfaları'na](../../c-runtime-library/code-pages.md)bakın. Bu üç işlev aynı şekilde çalışır. Bu işlevler, yerel ayarlardan etkilenir— **_l** sonek olmayan sürümler, yerel ayarlara bağımlı davranışları için geçerli yerel ayarları kullanır; **_l** soneki olan sürümler bunun yerine geçirilen *yerel alanı* kullanır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

Tüm bu işlevler parametrelerini doğrular. *String1* veya *string2* null işaretçisi ise, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler **_NLSCMPERROR** döndürdü ve **EINVAL'e** **errno** ayarlayın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsncicmp**|**_strnicmp**|**_mbsnicmp**|**_wcsnicmp**|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsncicmp_l**|**_strnicmp_l**|**_mbsnicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strnicmp**, **_strnicmp_l**|\<string.h>|
|**_wcsnicmp**, **_wcsnicmp_l**|\<string.h> \<veya wchar.h>|
|**_mbsnicmp**, **_mbsnicmp_l**|\<mbstring.h>|

Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

[strncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)için örneğe bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
