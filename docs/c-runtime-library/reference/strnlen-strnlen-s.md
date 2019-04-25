---
title: strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l
ms.date: 11/04/2016
apiname:
- wcsnlen
- strnlen_s
- _mbstrnlen
- _mbsnlen_l
- _mbstrnlen_l
- strnlen
- wcsnlen_s
- _mbsnlen
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
ms.openlocfilehash: 960d57ed8c2b1d1dbc6843932b8c76fef35c34a0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62209676"
---
# <a name="strnlen-strnlens-wcsnlen-wcsnlens-mbsnlen-mbsnlenl-mbstrnlen-mbstrnlenl"></a>strnlen, strnlen_s, wcsnlen, wcsnlen_s, _mbsnlen, _mbsnlen_l, _mbstrnlen, _mbstrnlen_l

Geçerli yerel ayarı veya içinde geçen bir kullanarak bir dizenin uzunluğunu alır. Bunlar daha güvenli sürümleri [strlen, wcslen, _mbslen, _mbslen_l, _mbstrlen, _mbstrlen_l](strlen-wcslen-mbslen-mbslen-l-mbstrlen-mbstrlen-l.md).

> [!IMPORTANT]
> **_mbsnlen**, **_mbsnlen_l**, **_mbstrnlen**, ve **_mbstrnlen_l** Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*str*<br/>
Null ile sonlandırılmış dize.

*numberOfElements*<br/>
Dize arabelleğinin boyutu.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevler, sondaki null karakter hariç dizesindeki karakterlerin sayısını döndürür. İlk null Sonlandırıcı ise *numberOfElements* dizenin bayt (veya geniş karakterler için **wcsnlen**), ardından *numberOfElements* döndürülür hata koşulu belirtin; null ile sonlandırılmış dizeler sahip olan kesinlikle az *numberOfElements*.

**_mbstrnlen** ve **_mbstrnlen_l** dize geçersiz bir çok baytlı karakter içeriyorsa, -1 döndürür.

## <a name="remarks"></a>Açıklamalar

> [!NOTE]
> **strnlen** yerine değil **strlen**; **strnlen** yalnızca bilinen boyutunun arabellekteki güvenilmeyen gelen verilerin boyutunu hesaplamak için kullanılması amaçlanmıştır — Örneğin, bir ağ paketi. **strnlen** uzunluğunu hesaplar ama Sonlandırılmamış dize arabellek sonunun yol değil. Diğer durumlarda, kullanın **strlen**. (Aynı geçerlidir **wcsnlen**, **_mbsnlen**, ve **_mbstrnlen**.)

Bu işlevlerin her biri, karakter sayısını döndürür *str*, sondaki boş karakter dahil değil. Ancak, **strnlen** ve **strnlen_s** dize bir tek baytlı karakter dizesi olarak yorumlar ve çok baytlı bir dize içeriyor olsa bile bu nedenle, dönüş değeri her zaman bayt sayısına eşit karakter. **wcsnlen** ve **wcsnlen_s** geniş karakterli sürümleridir **strnlen** ve **strnlen_s** sırasıyla; bağımsız değişkenler için **wcsnlen**  ve **wcsnlen_s** karakter sayısı olan geniş karakter birimleriyle ve geniş karakterli dizelerdir. Aksi takdirde, **wcsnlen** ve **strnlen** gibi aynı şekilde davranır **strnlen_s** ve **wcsnlen_s**.

**strnlen**, **wcsnlen**, ve **_mbsnlen** kendi parametrelerini doğrulamazlar. Varsa *str* olduğu **NULL**, erişim ihlali oluşur.

**strnlen_s** ve **wcsnlen_s** kendi parametrelerini doğrular. Varsa *str* olduğu **NULL**, İşlevler, 0 döndürür.

**_mbstrnlen** Ayrıca kendi parametrelerini doğrular. Varsa *str* olduğu **NULL**, veya *numberOfElements* büyüktür **INT_MAX**, **_mbstrnlen** bölümünde anlatıldığı gibi geçersiz parametre özel durum oluşturur [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **_mbstrnlen** ayarlar **errno** için **EINVAL** ve -1 döndürür.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcsnlen**|**strnlen**|**strnlen**|**wcsnlen**|
|**_tcscnlen**|**strnlen**|**_mbsnlen**|**wcsnlen**|
|**_tcscnlen_l**|**strnlen**|**_mbsnlen_l**|**wcsnlen**|

**_mbsnlen** ve **_mbstrnlen** bir çok baytlı karakter dizesi içinde birden çok baytlı karakter sayısını döndürür. **_mbsnlen** tanır çok baytlı kod sayfasına göre çok baytlı karakter sıralarını şu anda kullanımda veya geçirilen yerel ayara göre; çok baytlı karakter geçerliliğini test yok. **_mbstrnlen** çok baytlı karakter geçerliliğini sınar ve çok baytlı karakter sıralarını tanır. Geçirilen dize **_mbstrnlen** geçersiz bir çok baytlı karakter içeren **errno** ayarlanır **EILSEQ**.

Çıkış değeri ayarından etkilenir **LC_CTYPE** yerel ayarının kategori ayarına; bkz: [setlocale, _wsetlocale](setlocale-wsetlocale.md) daha fazla bilgi için. Sürücüler, yoksa dışında bu işlevlerin sürümleri özdeş sahip **_l** soneki, yerel ayara bağımlı Bu davranış ve sahip sürümler için geçerli yerel ayarı kullanır **_l** soneki Bunun yerine iletilen yerel ayar parametresini kullanın. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strnlen**, **strnlen_s**|\<String.h >|
|**wcsnlen**, **wcsnlen_s**|\<String.h > veya \<wchar.h >|
|**_mbsnlen**, **_mbsnlen_l**|\<Mbstring.h >|
|**_mbstrnlen**, **_mbstrnlen_l**|\<stdlib.h >|

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

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md)<br/>
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
