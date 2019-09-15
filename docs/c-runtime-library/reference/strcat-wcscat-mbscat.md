---
title: strcat, wcscat, _mbscat
ms.date: 11/04/2016
api_name:
- _mbscat
- wcscat
- strcat
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbscat
- _ftcscat
- _tcscat
- strcat
- wcscat
helpviewer_keywords:
- concatenating strings
- mbscat function
- _ftcscat function
- _tcscat function
- ftcscat function
- strcat function
- strings [C++], appending
- _mbscat function
- tcscat function
- strings [C++], concatenating
- appending strings
- wcscat function
ms.assetid: c89c4ef1-817a-44ff-a229-fe22d06ba78a
ms.openlocfilehash: 973c54c18e941b29526cb3e9b1cadb98f6582c4a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958269"
---
# <a name="strcat-wcscat-_mbscat"></a>strcat, wcscat, _mbscat

Bir dize ekler. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [strcat_s, wcscat_s, _mbscat_s](strcat-s-wcscat-s-mbscat-s.md).

> [!IMPORTANT]
> **_mbscat_s** Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
char *strcat(
   char *strDestination,
   const char *strSource
);
wchar_t *wcscat(
   wchar_t *strDestination,
   const wchar_t *strSource
);
unsigned char *_mbscat(
   unsigned char *strDestination,
   const unsigned char *strSource
);
template <size_t size>
char *strcat(
   char (&strDestination)[size],
   const char *strSource
); // C++ only
template <size_t size>
wchar_t *wcscat(
   wchar_t (&strDestination)[size],
   const wchar_t *strSource
); // C++ only
template <size_t size>
unsigned char *_mbscat(
   unsigned char (&strDestination)[size],
   const unsigned char *strSource
); // C++ only
```

### <a name="parameters"></a>Parametreler

*strDestination*<br/>
Null ile sonlandırılmış hedef dizesi.

*strSource*<br/>
Null ile sonlandırılmış kaynak dizesi.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, hedef dizeyi (*strDestination*) döndürür. Bir hatayı göstermek için hiçbir dönüş değeri ayrılmadı.

## <a name="remarks"></a>Açıklamalar

**Strcat** Işlevi *strSource* 'u *strDestination* öğesine ekler ve elde edilen dizeyi null karakterle sonlandırır. *StrSource* başlangıç karakteri, *strDestination*'ın Sonlandırıcı null karakterinin üzerine yazar. Kaynak ve hedef dizeler çakışırsa **strcat** 'in davranışı tanımsızdır.

> [!IMPORTANT]
> **Strcat** , *strSource*' a eklemeden önce *strDestination* 'ta yeterli alanı denetlemediğinden, arabellek taşmalarının olası bir nedeni vardır. Bunun yerine [strncat](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md) kullanmayı düşünün.

**wcscat** ve **_mbscat** , **strcat**'in geniş karakterli ve çok baytlı karakter sürümleridir. **Wcscat** bağımsız değişkenleri ve dönüş değeri geniş karakterli dizelerdir; **_mbscat** , çok baytlı karakter dizeleridir. Bu üç işlev, aynı şekilde davranır.

' C++De, bu işlevlerde bu işlevlerin daha yeni ve güvenli karşılıkları çağıran şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscat**|**strcat**|**_mbscat**|**wcscat**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strcat**|\<String. h >|
|**wcscat**|\<String. h > veya \<wchar. h >|
|**_mbscat**|\<mbstring. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Strcpy](strcpy-wcscpy-mbscpy.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenleme](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
