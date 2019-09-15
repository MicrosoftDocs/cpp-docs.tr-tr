---
title: strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l
ms.date: 11/04/2016
api_name:
- wcsnlen
- strnlen_s
- _mbstrnlen
- _mbsnlen_l
- _mbstrnlen_l
- strnlen
- wcsnlen_s
- _mbsnlen
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
- wcsnlen
- strnlen_s
- _mbsnlen
- _mbsnlen_l
- _tcsnlen
- _tcscnlen
- _mbstrnlen_l
- wcsnlen_s
- _mbstrnlen
- strnlen
- _tcscnlen_l
helpviewer_keywords:
- _tcscnlen function
- _mbstrnlen function
- _mbsnlen_l function
- lengths, strings
- mbstrnlen function
- mbsnlen_l function
- _mbstrnlen_l function
- _tcscnlen_l function
- wcsnlen_l function
- _tcsnlen function
- _mbsnlen function
- strnlen function
- mbsnlen function
- wcsnlen_s function
- strnlen_s function
- mbstrnlen_l function
- wcsnlen function
- string length
- strnlen_l function
ms.assetid: cc05ce1c-72ea-4ae4-a7e7-4464e56e5f80
ms.openlocfilehash: 6613c79bd9637b857dbf825eca2b37c71c154bec
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70947007"
---
# <a name="strnlen-strnlen_s-wcsnlen-wcsnlen_s-_mbsnlen-_mbsnlen_l-_mbstrnlen-_mbstrnlen_l"></a>strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l

Geçerli yerel ayarı veya geçirilen birini kullanarak bir dizenin uzunluğunu alır. Bu [, strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md)'ın daha güvenli sürümleridir.

> [!IMPORTANT]
> **_mbsnlen**, **_mbsnlen_l**, **_mbstrnlen**ve **_mbstrnlen_l** Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
size_t strnlen(
   const char *str,
   size_t numberOfElements
);
size_t strnlen_s(
   const char *str,
   size_t numberOfElements
);
size_t wcsnlen(
   const wchar_t *str,
   size_t numberOfElements
);
size_t wcsnlen_s(
   const wchar_t *str,
   size_t numberOfElements
);
size_t _mbsnlen(
   const unsigned char *str,
   size_t numberOfElements
);
size_t _mbsnlen_l(
   const unsigned char *str,
   size_t numberOfElements,
   _locale_t locale
);
size_t _mbstrnlen(
   const char *str,
   size_t numberOfElements
);
size_t _mbstrnlen_l(
   const char *str,
   size_t numberOfElements,
   _locale_t locale
);
```

### <a name="parameters"></a>Parametreler

*üstbilgisine*<br/>
Null ile sonlandırılmış dize.

*numberOfElements*<br/>
Dize arabelleğinin boyutu.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevler, sonlandıran null karakteri dahil değil dizedeki karakter sayısını döndürür. Dizenin ilk *numberOfElements* baytları içinde (veya **wcsnlen**için geniş karakterler) null Sonlandırıcı yoksa, hata koşulunu göstermek için *numberOfElements* döndürülür; null ile sonlandırılmış dizeler *Numberoföğelerinden*tamamen daha az uzunluklara sahiptir.

dize geçersiz bir çok baytlı karakter içeriyorsa **_mbstrnlen** ve **_mbstrnlen_l** Return-1 döndürür.

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> **strnlen** , **strlen**için bir değiştirme değil; **strnlen** , yalnızca gelen güvenilmeyen verilerin boyutunu bilinen boyut (örneğin, bir ağ paketi) arabelleğinde hesaplamak için kullanılmak üzere tasarlanmıştır. **strnlen** uzunluğu hesaplar, ancak dize sonlandırılmamışsa arabelleğin sonunu geçti. Diğer durumlar için, **strlen**kullanın. (Aynı, **wcsnlen**, **_mbsnlen**ve **_mbstrnlen**için geçerlidir.)

Bu işlevlerin her biri, sonlandıran null karakteri dahil değil *Str*içindeki karakter sayısını döndürür. Ancak, **strnlen** ve **strnlen_s** dizeyi tek baytlık bir karakter dizesi olarak yorumlar ve bu nedenle, dize çok baytlı karakterler içerse de, dönüş değeri her zaman bayt sayısına eşittir. **wcsnlen** ve **wcsnlen_s** sırasıyla **strnlen** ve **strnlen_s** 'in geniş karakterli sürümleridir; **wcsnlen** ve **wcsnlen_s** için bağımsız değişkenler geniş karakterli dizelerdir ve karakter sayısı geniş karakter birimleridir. Aksi halde, **wcsnlen** ve **strnlen** , **strnlen_s** ve **wcsnlen_s**gibi aynı şekilde davranır.

**strnlen**, **wcsnlen**ve **_mbsnlen** parametrelerini doğrulamaz. *Str* **null**ise, erişim ihlali oluşur.

**strnlen_s** ve **wcsnlen_s** parametrelerini doğrulayın. *Str* **null**ise, işlevler 0 döndürür.

**_mbstrnlen** Ayrıca parametrelerini de doğrular. *Str* **null**ise veya *numberOfElements* değeri **INT_MAX**' den büyükse, **_mbstrnlen** [parametresi, parametre doğrulamasında](../../c-runtime-library/parameter-validation.md)açıklanan şekilde geçersiz bir parametre özel durumu oluşturur. Yürütmenin devam etmesine izin veriliyorsa **_mbstrnlen** , **errno** değerini **EINVAL** olarak ayarlar ve-1 döndürür.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnlen**|**strnlen**|**strnlen**|**wcsnlen**|
|**_tcscnlen**|**strnlen**|**_mbsnlen**|**wcsnlen**|
|**_tcscnlen_l**|**strnlen**|**_mbsnlen_l**|**wcsnlen**|

**_mbsnlen** ve **_mbstrnlen** çok baytlı karakter dizesindeki çok baytlı karakterlerin sayısını döndürür. **_mbsnlen** kullanımda olan çok baytlı kod sayfasına göre veya geçirilen yerel ayara göre çok baytlı karakter dizilerini tanır; çok baytlı karakter geçerliliği için test etmez. **_mbstrnlen** çok baytlı karakter geçerliliği için testler ve çok baytlı karakter dizilerini tanır. **_Mbstrnlen** öğesine geçirilen dize geçersiz bir çok baytlı karakter içeriyorsa, **errno** **eilseq**olarak ayarlanır.

Çıkış değeri yerel ayarın **LC_CTYPE** kategori ayarı ayarından etkilenir; daha fazla bilgi için bkz. [setlocale, _wsetlocale](setlocale-wsetlocale.md) . Bu işlevlerin sürümleri aynıdır, çünkü **_l** sonekine sahip olmayan bu, yerel ayara bağımlı davranış için geçerli yerel ayarı kullanır ve bunun yerine **_l** sonekine sahip olan sürümler, geçirilen yerel ayar parametresini kullanır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strnlen**, **strnlen_s**|\<String. h >|
|**wcsnlen**, **wcsnlen_s**|\<String. h > veya \<wchar. h >|
|**_mbsnlen**, **_mbsnlen_l**|\<mbstring. h >|
|**_mbstrnlen**, **_mbstrnlen_l**|\<Stdlib. h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_strnlen.c

#include <string.h>

int main()
{
   // str1 is 82 characters long. str2 is 159 characters long

   char* str1 = "The length of a string is the number of characters\n"
               "excluding the terminating null.";
   char* str2 = "strnlen takes a maximum size. If the string is longer\n"
                "than the maximum size specified, the maximum size is\n"
                "returned rather than the actual size of the string.";
   size_t len;
   size_t maxsize = 100;

   len = strnlen(str1, maxsize);
   printf("%s\n Length: %d \n\n", str1, len);

   len = strnlen(str2, maxsize);
   printf("%s\n Length: %d \n", str2, len);
}
```

```Output
The length of a string is the number of characters
excluding the terminating null.
Length: 82

strnlen takes a maximum size. If the string is longer
than the maximum size specified, the maximum size is
returned rather than the actual size of the string.
Length: 100
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenleme](../../c-runtime-library/string-manipulation-crt.md)<br/>
[locale](../../c-runtime-library/locale.md)<br/>
[Çok Baytlı Karakter Sıralarının Yorumu](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[setlocale, _wsetlocale](setlocale-wsetlocale.md)<br/>
[strncat, _strncat_l, wcsncat, _wcsncat_l, _mbsncat, _mbsncat_l](strncat-strncat-l-wcsncat-wcsncat-l-mbsncat-mbsncat-l.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[strcoll İşlevleri](../../c-runtime-library/strcoll-functions.md)<br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)<br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md)<br/>
[_strset, _strset_l, _wcsset, _wcsset_l, _mbsset, _mbsset_l](strset-strset-l-wcsset-wcsset-l-mbsset-mbsset-l.md)<br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
