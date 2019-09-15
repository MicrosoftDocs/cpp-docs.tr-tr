---
title: strcpy_s, wcscpy_s, _mbscpy_s, _mbscpy_s_l
ms.date: 01/22/2019
api_name:
- wcscpy_s
- _mbscpy_s
- _mbscpy_s_l
- strcpy_s
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
ms.openlocfilehash: 12c20abc13846388b7a303af4e29de3cd2a60fed
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70957853"
---
# <a name="strcpy_s-wcscpy_s-_mbscpy_s-_mbscpy_s_l"></a>strcpy_s, wcscpy_s, _mbscpy_s, _mbscpy_s_l

Bir dizeyi kopyalar. [Strcpy, wcscpy, _mbscvy](strcpy-wcscpy-mbscpy.md) uygulamasının bu SÜRÜMLERINDE, [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri vardır.

> [!IMPORTANT]
> **_mbscpy_s** ve **_mbscpy_s_l** , Windows çalışma zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

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

*HD*<br/>
Hedef dize arabelleğinin konumu.

*dest_size*<br/>
Daraltma ve çok baytlı işlevler için **karakter** birimlerindeki hedef dize arabelleğinin boyutu ve geniş işlevler için **wchar_t** birimleri. Bu değer sıfırdan büyük ve **RSIZE_MAX**değerinden büyük olmalıdır.

*YN*<br/>
Null ile sonlandırılmış kaynak dize arabelleği.

*ayarlar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Başarılıysa sıfır; Aksi takdirde bir hata.

### <a name="error-conditions"></a>Hata koşulları

|*HD*|*dest_size*|*YN*|Dönüş değeri|*Hedef* içeriği|
|----------------------|------------------------|-----------------|------------------|----------------------------------|
|**DEĞER**|Kaydedilmemiş|Kaydedilmemiş|**EINVAL**|değiştirilmedi|
|Kaydedilmemiş|Kaydedilmemiş|**DEĞER**|**EINVAL**|*hedef* [0] 0 olarak ayarlandı|
|Kaydedilmemiş|0 veya çok küçük|Kaydedilmemiş|**ERANGE**|*hedef* [0] 0 olarak ayarlandı|

## <a name="remarks"></a>Açıklamalar

**Strcpy_s** işlevi, sonlandırma null karakteri dahil *src*adresinin içeriğini *hedef*tarafından belirtilen konuma kopyalar. Hedef dize, kaynak dizeyi ve Sonlandırıcı null karakterini barındıracak kadar büyük olmalıdır. Kaynak ve hedef dizeler çakıştığında **strcpy_s** davranışı tanımsızdır.

**wcscpy_s** , **strcpy_s**öğesinin geniş karakterli sürümüdür ve **_mbscpy_s** çok baytlı karakter sürümüdür. **Wcscpy_s** bağımsız değişkenleri geniş karakterli dizelerdir; **_mbscpy_s** ve **_mbscpy_s_l** , çok baytlı karakter dizeleridir. Bu işlevler, aynı şekilde davranır. **_mbscpy_s_l** , geçerli yerel ayar yerine geçirilen yerel ayar parametresini kullanması dışında **_mbscpy_s** ile aynıdır. Daha fazla bilgi için bkz. [locale](../../c-runtime-library/locale.md).

Hedef *veya* *src* null bir işaretçisiyse veya hedef dize boyutu *Dest_size* çok küçükse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **EINVAL** döndürür ve *dest* veya *src* null bir **işaretçi olduğunda** **errno** , **EINVAL** **olarak** **ayarlanır ve** hedef dize çok küçük.

Başarılı bir yürütme sonrasında, hedef dize her zaman null ile sonlandırılır.

' C++De, bu işlevlerin kullanımı, bir boyut bağımsız değişkeni belirtmek zorunda kalmazsınız ve daha eski, daha az güvenli işlevleri daha yeni, daha güvenli bir şekilde otomatik olarak değiştirmek için arabellek uzunluğunu otomatik olarak çıkarsanbilecekleri şablon aşırı yüklemeleri tarafından basitleştirilmiştir ortaklarınıza. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Bu işlevlerin hata ayıklama Kitaplığı sürümleri ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_Crtsetdebugfillthreshold](crtsetdebugfillthreshold.md)kullanın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscpy_s**|**strcpy_s**|**_mbscpy_s**|**wcscpy_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strcpy_s**|\<String. h >|
|**wcscpy_s**|\<String. h > veya \<wchar. h >|
|**_mbscpy_s**|\<mbstring. h >|

Bu işlevler, Microsoft 'a özgüdür. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Üretim kalitesi kodundan farklı olarak, bu örnek hataları denetlemeden güvenli dize işlevlerini çağırır:

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

Kod oluştururken C++ , şablon sürümlerinin kullanımı daha kolay olabilir.

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

[Dize düzenleme](../../c-runtime-library/string-manipulation-crt.md) <br/>
[strcat, wcscat, _mbscat, _mbdağınık _l](strcat-wcscat-mbscat.md) <br/>
[strcmp, wcscmp, _mbscmp, _mbscmp_l](strcmp-wcscmp-mbscmp.md) <br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md) <br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md) <br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md) <br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md) <br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md) <br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
