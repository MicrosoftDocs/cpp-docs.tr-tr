---
title: strcpy_s, wcscpy_s, _mbscpy_s, _mbscpy_s_l
ms.date: 01/22/2019
apiname:
- wcscpy_s
- _mbscpy_s
- _mbscpy_s_l
- strcpy_s
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
apitype: DLLExport
f1_keywords:
- strcpy_s
- _mbscpy_s
- _mbscpy_s_l
- _tcscpy_s
- wcscpy_s
helpviewer_keywords:
- strcpy_s function
- _tcscpy_s function
- _mbscpy_s function
- _mbscpy_s_l function
- copying strings
- strings [C++], copying
- tcscpy_s function
- wcscpy_s function
ms.assetid: 611326f3-7929-4a5d-a465-a4683af3b053
ms.openlocfilehash: 5dec0c44519b78a3c4a98c51f8b8ca9bc3f54a7c
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/04/2019
ms.locfileid: "55702719"
---
# <a name="strcpys-wcscpys-mbscpys-mbscpysl"></a>strcpy_s, wcscpy_s, _mbscpy_s, _mbscpy_s_l

Bir dizeyi kopyalar. Bu sürümleri [strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

> [!IMPORTANT]
> **_mbscpy_s** ve **_mbscpy_s_l** Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t strcpy_s(
   char *dest,
   rsize_t dest_size,
   const char *src
);
errno_t wcscpy_s(
   wchar_t *dest,
   rsize_t dest_size,
   const wchar_t *src
);
errno_t _mbscpy_s(
   unsigned char *dest,
   rsize_t dest_size,
   const unsigned char *src
);
errno_t _mbscpy_s_l(
   unsigned char *dest,
   rsize_t dest_size,
   const unsigned char *src,
   _locale_t locale
);
```

```cpp
// Template functions are C++ only:
template <size_t size>
errno_t strcpy_s(
   char (&dest)[size],
   const char *src
); // C++ only
template <size_t size>
errno_t wcscpy_s(
   wchar_t (&dest)[size],
   const wchar_t *src
); // C++ only
template <size_t size>
errno_t _mbscpy_s(
   unsigned char (&dest)[size],
   const unsigned char *src
); // C++ only
template <size_t size>
errno_t _mbscpy_s_l(
   unsigned char (&dest)[size],
   const unsigned char *src,
   _locale_t locale
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Hedef*<br/>
Hedef dize arabelleğinin konumu.

*dest_size*<br/>
Hedef dize arabelleğinin boyutu **char** dar ve çok baytlı İşlevler, birim ve **wchar_t** geniş işlevlerine yönelik birimleri. Bu değer, sıfırdan büyük ve büyüktür olmalıdır **RSIZE_MAX**.

*src*<br/>
Null ile sonlandırılmış kaynak dizesi arabelleği.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi takdirde bir hata oluştu.

### <a name="error-conditions"></a>Hata koşulları

|*Hedef*|*dest_size*|*src*|Dönüş değeri|İçeriğini *dest*|
|----------------------|------------------------|-----------------|------------------|----------------------------------|
|**NULL**|Tüm|Tüm|**EINVAL**|değiştirilmedi|
|Tüm|Tüm|**NULL**|**EINVAL**|*Hedef*0 olarak ayarlanırsa [0]|
|Tüm|0 veya çok küçük|Tüm|**ERANGE**|*Hedef*0 olarak ayarlanırsa [0]|

## <a name="remarks"></a>Açıklamalar

**Strcpy_s** işlevi adresindeki içeriğini kopyalar *src*, tarafından belirtilen konuma bir sonlandırıcı null karakter de dahil olmak üzere *dest*. Hedef dize kaynak dizeyi ve onu sonlandıran null karakteri alacak kadar büyük olmalıdır. Davranışını **strcpy_s** kaynak ve hedef dizeleri örtüştürürse tanımsızdır.

**wcscpy_s** öğesinin geniş karakterli sürümüdür **strcpy_s**, ve **_mbscpy_s** çok baytlı karakter sürümüdür. Bağımsız değişkenleri **wcscpy_s** geniş karakterli dizelerdir; **_mbscpy_s** ve **_mbscpy_s_l** çok baytlı karakter dizeleridir. Bu işlevler, aynı şekilde davranır. **_mbscpy_s_l** aynıdır **_mbscpy_s** geçerli yerel ayarı yerine iletilen yerel ayar parametresini kullanması hariç, aynıdır. Daha fazla bilgi için [yerel](../../c-runtime-library/locale.md).

Varsa *dest* veya *src* null bir işaretçiyse veya hedef dize boyutu *dest_size* içindeaçıklandığıgibigeçersizparametreişleyicisiçağrılır,çokküçükolduğu[Parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler döndürür **EINVAL** ayarlayıp **errno** için **EINVAL** olduğunda *dest* veya  *src* null bir işaretçiyse ve döndürmeleri **ERANGE** ayarlayıp **errno** için **ERANGE** zaman hedef dize çok küçük.

Başarılı yürütme sonrasında hedef dize her zaman null sonlandırılmıştır.

C++ dilinde bu işlevlerin kullanımı, uzunluğun otomatik olarak çıkarabilir ve böylece bir boyut bağımsız değişkeni belirtmeniz gerekmez şablon aşırı yüklemeleriyle basitleştirilmiştir ve bunlar otomatik olarak eski ve daha az güvenli işlevleri, daha yeni değiştirir daha güvenli ortaklarınıza. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama kitaplığı sürümleri ilk arabellek 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscpy_s**|**strcpy_s**|**_mbscpy_s**|**wcscpy_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strcpy_s**|\<String.h >|
|**wcscpy_s**|\<String.h > veya \<wchar.h >|
|**_mbscpy_s**|\<Mbstring.h >|

Bu işlevler Microsoft özgüdür. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Üretim kalitesinde kod, bu örnek, hataları denetlemeden güvenli dize işlevleri çağırır:

```C
// crt_strcpy_s.c
// Compile by using: cl /W4 crt_strcpy_s.c
// This program uses strcpy_s and strcat_s
// to build a phrase.

#include <string.h>     // for strcpy_s, strcat_s
#include <stdlib.h>     // for _countof
#include <stdio.h>      // for printf
#include <errno.h>      // for return values

int main(void)
{
    char string[80];

    strcpy_s(string, _countof(string), "Hello world from ");
    strcat_s(string, _countof(string), "strcpy_s ");
    strcat_s(string, _countof(string), "and ");
    strcat_s(string, _countof(string), "strcat_s!");

    printf("String = %s\n", string);
}
```

```Output
String = Hello world from strcpy_s and strcat_s!
```

Şablonu sürümleri, C++ kodu oluştururken, kullanımı daha kolay olabilir.

```cpp
// crt_wcscpy_s.cpp
// Compile by using: cl /EHsc /W4 crt_wcscpy_s.cpp
// This program uses wcscpy_s and wcscat_s
// to build a phrase.

#include <cstring>  // for wcscpy_s, wcscat_s
#include <cstdlib>  // for _countof
#include <iostream> // for cout, includes <cstdlib>, <cstring>
#include <errno.h>  // for return values

int main(void)
{
    wchar_t string[80];
    // using template versions of wcscpy_s and wcscat_s:
    wcscpy_s(string, L"Hello world from ");
    wcscat_s(string, L"wcscpy_s ");
    wcscat_s(string, L"and ");
    // of course we can supply the size explicitly if we want to:
    wcscat_s(string, _countof(string), L"wcscat_s!");

    std::wcout << L"String = " << string << std::endl;
}
```

```Output
String = Hello world from wcscpy_s and wcscat_s!
```

## <a name="see-also"></a>Ayrıca bkz.

[Dize düzenlemesi](../../c-runtime-library/string-manipulation-crt.md) <br/>
[strcat, wcscat, _mbscat, _mbscat_l](strcat-wcscat-mbscat.md) <br/>
[strcmp, wcscmp, _mbscmp, _mbscmp_l](strcmp-wcscmp-mbscmp.md) <br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md) <br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md) <br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md) <br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md) <br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md) <br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
