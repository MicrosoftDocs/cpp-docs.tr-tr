---
title: strcpy_s, wcscpy_s, _mbscpy_s, _mbscpy_s_l
ms.date: 4/2/2020
api_name:
- wcscpy_s
- _mbscpy_s
- _mbscpy_s_l
- strcpy_s
- _o__mbscpy_s
- _o__mbscpy_s_l
- _o_strcpy_s
- _o_wcscpy_s
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
ms.openlocfilehash: ac68d2fb86a43d7114b3b0e7651f5ae4367aa44b
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81358704"
---
# <a name="strcpy_s-wcscpy_s-_mbscpy_s-_mbscpy_s_l"></a>strcpy_s, wcscpy_s, _mbscpy_s, _mbscpy_s_l

Bir dize kopyalar. [Strcpy, wcscpy, _mbscpy](strcpy-wcscpy-mbscpy.md) bu sürümleri [crt Güvenlik Özellikleri](../../c-runtime-library/security-features-in-the-crt.md)açıklandığı gibi güvenlik geliştirmeleri var.

> [!IMPORTANT]
> **_mbscpy_s** ve **_mbscpy_s_l,** Windows Runtime'da çalışan uygulamalarda kullanılamaz. Daha fazla bilgi için Evrensel [Windows Platformu uygulamalarında desteklenmeyen CRT işlevlerine](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)bakın.

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

*Dest*<br/>
Hedef dize arabelleği konumu.

*dest_size*<br/>
Dar ve çok bayt lı işlevler için **char** birimlerindeki hedef dize arabelleği ve geniş işlevler için **wchar_t** birimlerinin boyutu. Bu değer sıfırdan büyük olmalı ve **RSIZE_MAX**büyük olmamalıdır.

*src*<br/>
Null-sonlandırılan kaynak dize arabelleği.

*Yerel ayar*<br/>
Kullanılacak yerel yer.

## <a name="return-value"></a>Dönüş Değeri

Başarılı olursa sıfır; aksi takdirde, bir hata.

### <a name="error-conditions"></a>Hata Koşulları

|*Dest*|*dest_size*|*src*|Döndürülen değer|*Dest'in* içindekiler|
|----------------------|------------------------|-----------------|------------------|----------------------------------|
|**Null**|herhangi bir|herhangi bir|**Eınval**|değiştirilmemiş|
|herhangi bir|herhangi bir|**Null**|**Eınval**|*dest*[0] 0 olarak ayarlanmış|
|herhangi bir|0 veya çok küçük|herhangi bir|**Erange**|*dest*[0] 0 olarak ayarlanmış|

## <a name="remarks"></a>Açıklamalar

**strcpy_s** işlevi, *src*adresindeki içeriği , sonlandırıcı null karakter de dahil olmak üzere, *dest*tarafından belirtilen konuma kopyalar. Hedef dize kaynak dize ve sonlandırıcı null karakteri tutmak için yeterince büyük olmalıdır. Kaynak ve hedef dizeleri çakışıyorsa **strcpy_s** davranışı tanımsızdır.

**wcscpy_s** **strcpy_s**geniş karakterli versiyonudur ve **_mbscpy_s** multibayt karakter versiyonudur. **wcscpy_s** bağımsız değişkenleri geniş karakterli dizeleri vardır; **_mbscpy_s** ve **_mbscpy_s_l** çok bayt karakterli dizeleri vardır. Bu işlevler aynı şekilde başka türlü çalışır. **_mbscpy_s_l,** geçerli yerel alan yerine geçirilen yerel parametreyi kullanması dışında **_mbscpy_s** ile aynıdır. Daha fazla bilgi için [Yerel'e](../../c-runtime-library/locale.md)bakın.

*Dest* veya *src* null işaretçisi ise veya hedef dize boyutu *dest_size* çok küçükse, geçersiz parametre işleyicisi [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütmedevam etmesine izin verilirse, bu işlevler EINVAL döndürür ve *dest* veya *src* null işaretçi olduğunda **EINVAL'a** **errno** ayarlar ve hedef dize çok küçük olduğunda **ERANGE'yi** döndürür ler ve **errno'yu** **ERANGE'ye** ayarlarlar. **EINVAL**

Başarılı bir yürütme üzerine, hedef dize her zaman null-sonlandırılır.

C++'da, bu işlevlerin kullanımı, bir boyut bağımsız değişkeni belirtmeniz gerekmeden arabellek uzunluğunu otomatik olarak çıkarabilen şablon aşırı yüklemeleri ile basitleştirilir ve bunlar daha eski, daha az güvenli işlevleri daha yeni ve daha güvenli karşılıklarıyla otomatik olarak değiştirebilir. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

Bu işlevlerin hata ayıklama kitaplığı sürümleri önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_tcscpy_s**|**strcpy_s**|**_mbscpy_s**|**wcscpy_s**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**strcpy_s**|\<string.h>|
|**wcscpy_s**|\<string.h> \<veya wchar.h>|
|**_mbscpy_s**|\<mbstring.h>|

Bu işlevler Microsoft'a özgütür. Ek uyumluluk bilgileri için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Üretim kalite kodunun aksine, bu örnek hataları kontrol etmeden güvenli dize işlevlerini çağırır:

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

C++ kodu oluşturulurken şablon sürümlerinin kullanımı daha kolay olabilir.

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

[Dize Düzenlemesi](../../c-runtime-library/string-manipulation-crt.md) <br/>
[strcat, wcscat, _mbscat, _mbscat_l](strcat-wcscat-mbscat.md) <br/>
[strcmp, wcscmp, _mbscmp, _mbscmp_l](strcmp-wcscmp-mbscmp.md) <br/>
[strncat_s, _strncat_s_l, wcsncat_s, _wcsncat_s_l, _mbsncat_s, _mbsncat_s_l](strncat-s-strncat-s-l-wcsncat-s-wcsncat-s-l-mbsncat-s-mbsncat-s-l.md) <br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md) <br/>
[strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md) <br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md) <br/>
[strrchr, wcsrchr, _mbsrchr, _mbsrchr_l](strrchr-wcsrchr-mbsrchr-mbsrchr-l.md) <br/>
[strspn, wcsspn, _mbsspn, _mbsspn_l](strspn-wcsspn-mbsspn-mbsspn-l.md)<br/>
