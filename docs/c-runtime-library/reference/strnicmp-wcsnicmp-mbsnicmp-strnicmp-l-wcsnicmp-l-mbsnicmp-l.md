---
title: _strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l
ms.date: 11/04/2016
api_name:
- _wcsnicmp
- _strnicmp_l
- _wcsnicmp_l
- _strnicmp
- _mbsnicmp
- _mbsnicmp_l
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
ms.openlocfilehash: 6d1645c33684f5a0fbabc2119592c39a7df97ca3
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70947129"
---
# <a name="_strnicmp-_wcsnicmp-_mbsnicmp-_strnicmp_l-_wcsnicmp_l-_mbsnicmp_l"></a>_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l

İki dizenin belirtilen karakter sayısını, büyük/küçük harfe göre karşılaştırır.

> [!IMPORTANT]
> **_mbsnıcmp** ve **_mbsnicmp_l** Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*biriktirme*<br/>
Karşılaştırılacak karakter sayısı.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Aşağıdaki gibi alt dizeler arasındaki ilişkiyi gösterir.

|Dönüş değeri|Açıklama|
|------------------|-----------------|
|< 0|*Dize1* substring, *dize2* alt dizeden küçük.|
|0|*Dize1* substring, *dize2* alt dizesi ile aynıdır.|
|> 0|*Dize1* substring, *dize2* alt dizeden büyük.|

Bir parametre doğrulama hatası üzerinde bu işlevler, \<String. h > ve \<mbstring. h > tanımlanan **_NLSCMPERROR**döndürür.

## <a name="remarks"></a>Açıklamalar

**_Strnıcmp** işlevi, en çok, *Dize1* ve *dize2*' nin ilk *sayı* karakterlerini bir üst düzeyde karşılaştırır. Karşılaştırma, her karakter küçük harfe dönüştürülene bakılmaksızın gerçekleştirilir. **_strnıcmp** , **strncmp**'nin büyük/küçük harfe duyarlı bir sürümüdür. *Sayma* karakterleri karşılaştırılmadan önce her iki dizede de bir Sonlandırıcı null karakterine ulaşıldığında karşılaştırma biter. *Sayı* karakterleri karşılaştırılmadan önce bir dizede bir Sonlandırıcı null karakterine ulaşıldığında dizeler eşitse, daha kısa dize daha küçüktür.

ASCII tablosunda (' [', '\\', '] ', ' ^ ', ' _ ' ve '\`') 91 ' den 96 ' e kadar olan karakterler herhangi bir alfabetik karakterden daha az değerlendirilir. Bu sıralama, **stricmp**ile aynıdır.

**_wcsnıcmp** ve **_mbsnıcmp** , **_strnıcmp**'nin geniş karakterli ve çok baytlı karakter sürümleridir. **_Wcsnıcmp** bağımsız değişkenleri geniş karakterli dizelerdir; **_mbsnıcmp** olanlar çok baytlı karakter dizeleridir. **_mbsnıcmp** , geçerli çok baytlı kod sayfasına göre çok baytlı karakter dizilerini tanır ve hata üzerinde **_Nlscmperror** döndürür. Daha fazla bilgi için bkz. [kod sayfaları](../../c-runtime-library/code-pages.md). Bu üç işlev, aynı şekilde davranır. Bu işlevler yerel ayar ayarından etkilenir — **_l** sonekine sahip olmayan sürümler, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır; Bunun yerine **_l** sonekine sahip olan sürümler, geçirilen *yerel ayarı* kullanır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Bu işlevlerin hepsi parametrelerini doğrular. *Dize1* veya *dize2* , null Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **_Nlscmperror** döndürür ve **errno** öğesini **EINVAL**olarak ayarlayın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsncıcmp**|**_strnıcmp**|**_mbsnicmp**|**_wcsnıcmp**|
|**_tcsnıcmp**|**_strnıcmp**|**_mbsnbicmp**|**_wcsnıcmp**|
|**_tcsncicmp_l**|**_strnicmp_l**|**_mbsnicmp_l**|**_wcsnicmp_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_strnıcmp**, **_strnicmp_l**|\<String. h >|
|**_wcsnıcmp**, **_wcsnicmp_l**|\<String. h > veya \<wchar. h >|
|**_mbsnıcmp**, **_mbsnicmp_l**|\<mbstring. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

[Strncmp](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)örneğine bakın.

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenleme](../../c-runtime-library/string-manipulation-crt.md)<br/>
[strcat, wcscat, _mbscat](strcat-wcscat-mbscat.md)<br/>
[strcmp, wcscmp, _mbscmp](strcmp-wcscmp-mbscmp.md)<br/>
[strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
