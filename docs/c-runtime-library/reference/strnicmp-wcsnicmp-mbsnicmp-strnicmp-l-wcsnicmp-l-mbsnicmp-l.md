---
title: _strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
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
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 08dc7c899309abd65517f84fae73ee8988019e53
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="strnicmp-wcsnicmp-mbsnicmp-strnicmpl-wcsnicmpl-mbsnicmpl"></a>_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l
Belirtilen sayıda servis talebi dikkate almaksızın iki dize karakterlerini karşılaştırır.

> [!IMPORTANT]
> **_mbsnicmp** ve **_mbsnicmp_l** Windows çalışma zamanı'nda yürütme uygulamaları kullanılamaz. Daha fazla bilgi için bkz: [Evrensel Windows platformu uygulamaları desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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
Karşılaştırılacak null ile sonlandırılmış dizeler.

*Sayısı*<br/>
Karşılaştırılacak karakter sayısı.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Alt dizeler arasındaki ilişkiyi gibi gösterir.

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* alt dizesidir değerinden *dize2* substring.|
|0|*Dize1* alt dizesidir aynı *dize2* substring.|
|> 0|*Dize1* alt dizesidir büyük *dize2* substring.|

Üzerinde bir parametre doğrulama hatası, bu işlevlerin dönüş **_NLSCMPERROR**, içinde tanımlanan \<string.h > ve \<mbstring.h >.

## <a name="remarks"></a>Açıklamalar

**_Strnicmp** işlevi ordinally karşılaştırır, en fazla ilk *sayısı* karakterlerinden *Dize1* ve *dize2*. Karşılaştırma durum dikkate almaksızın küçük her karakter dönüştürme tarafından gerçekleştirilir. **_strnicmp** büyük küçük harf duyarsız bir sürümü **strncmp**. Karşılaştırma sonlandırma bir null karakter önce ya da dizesinde ulaşıldığında sona *sayısı* karakter karşılaştırılır. Dizeleri eşitse, ne zaman bir sonlandırma null karakter ulaşıldığında önce ya da dizesinde *sayısı* karakter karşılaştırılır, kısa daha düşük bir dizedir.

ASCII tablosundaki 96 91 karakterleri ('[','\\', ']', ' ^', '_' ve '\`') olarak değerinden alfabetik bir karakterle değerlendirin. Bu sıralama aynı **stricmp**.

**_wcsnicmp** ve **_mbsnicmp** joker karakter ve çok baytlı karakter sürümleri **_strnicmp**. Bağımsız değişkenleri **_wcsnicmp** joker karakter olan dizeleri; bu **_mbsnicmp** çok baytlı karakter dizeleri belirtilmiştir. **_mbsnicmp** geçerli birden çok baytlı kod sayfasına göre çok baytlı karakter sıralarının tanır ve döndürür **_NLSCMPERROR** bir hata. Daha fazla bilgi için bkz: [kod sayfaları](../../c-runtime-library/code-pages.md). Bu üç işlevler aynı şekilde aksi davranır. Bu işlevler yerel ayardan etkilenir — olmayan sürümleri **_l** yerel ayara bağımlı davranışlarını geçerli yerel kullanılmak soneki; olan sürümleri **_l** soneki Bunun yerine kullanın *yerel* olarak geçirilir. Daha fazla bilgi için bkz: [yerel ayar](../../c-runtime-library/locale.md).

Tüm bu işlevlerin kendi parametreleri doğrulayın. Her iki *Dize1* veya *dize2* null işaretçi açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş **_NLSCMPERROR** ve **errno** için **EINVAL**.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsncicmp**|**_strnicmp**|**_mbsnicmp**|**_wcsnicmp**|
|**_tcsnicmp**|**_strnicmp**|**_mbsnbicmp**|**_wcsnicmp**|
|**_tcsncicmp_l**|**_strnicmp_l**|**_mbsnicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strnicmp**, **_strnicmp_l**|< string.h >|
|**_wcsnicmp**, **_wcsnicmp_l**|< string.h > veya < wchar.h >|
|**_mbsnicmp**, **_mbsnicmp_l**|\<Mbstring.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Örneğin bkz [strncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md).

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
