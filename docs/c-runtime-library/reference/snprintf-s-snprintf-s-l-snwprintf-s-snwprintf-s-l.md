---
description: 'Hakkında daha fazla bilgi edinin: _snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l'
title: _snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l
ms.date: 3/9/2021
api_name:
- _snprintf_s
- _snprintf_s_l
- _snwprintf_s
- _snwprintf_s_l
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _snwprintf_s_l
- _sntprintf_s_l
- snprintf_s_l
- _snprintf_s_l
- _sntprintf_s
- _snprintf_s
- snprintf_s
- _snwprintf_s
- snwprintf_s_l
- snwprintf_s
- sntprintf_s
- sntprintf_s_l
helpviewer_keywords:
- _snprintf_s_l function
- _snwprintf_s_l function
- _sntprintf_s_l function
- snwprintf_s_l function
- snprintf_s function
- _snprintf_s function
- snprintf_s_l function
- _sntprintf_s function
- sntprintf_s_l function
- sntprintf_s function
- snwprintf_s function
- _snwprintf_s function
- formatted text [C++]
ms.openlocfilehash: 7bee7b376deda021dd1d03909ebd0d9b088689b9
ms.sourcegitcommit: b04b39940b0c1e265f80fc1951278fdb05a1b30a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102621444"
---
# <a name="_snprintf_s-_snprintf_s_l-_snwprintf_s-_snwprintf_s_l"></a>_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l

Biçimlendirilmiş verileri bir dizeye yazar. Bunlar, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklanan şekilde, güvenlik geliştirmeleriyle, [snprintf, _snprintf, _snprintf_l, _snwprintf _snwprintf_l](snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md) sürümleridir.

## <a name="syntax"></a>Sözdizimi

```C
int _snprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format [,
   argument] ...
);
int _snprintf_s_l(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   locale_t locale [,
   argument] ...
);
int _snwprintf_s(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const wchar_t *format [,
   argument] ...
);
int _snwprintf_s_l(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
template <size_t size>
int _snprintf_s(
   char (&buffer)[size],
   size_t count,
   const char *format [,
   argument] ...
); // C++ only
template <size_t size>
int _snwprintf_s(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format [,
   argument] ...
); // C++ only
```

### <a name="parameters"></a>Parametreler

*arabelleğin*<br/>
Çıktı için depolama konumu.

*sizeOfBuffer*<br/>
Çıktı için depolama konumunun boyutu. **_Snwprintf_s** için **_snprintf_s** veya **sözcüklerin** boyutu için **bayt** cinsinden boyut.

*biriktirme*<br/>
Depolanacak en fazla karakter sayısı veya [_TRUNCATE](../../c-runtime-library/truncate.md).

*formatını*<br/>
Biçim denetimi dizesi.

*değişkendir*<br/>
İsteğe bağlı bağımsız değişkenler.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

**_snprintf_s** , Sonlandırıcı null karakteri saymayan *arabellekte* depolanan karakter sayısını döndürür. **_snwprintf_s** , sondaki null geniş karakteri saymayan *arabellekte* depolanan geniş karakter sayısını döndürür.

Verileri depolamak için gereken depolama alanı ve bir Sonlandırıcı null değeri *sizeOfBuffer* değerini aşarsa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütme geçersiz parametre işleyiciden sonra devam ediyorsa, bu işlevler *arabelleği* boş bir dizeye ayarlar, **errno** , **ERANGE** ayarla ve-1 döndürür.

*Arabellek* veya *Biçim* **null** işaretçisiyse veya *sayı* sıfırdan küçükse veya eşitse, geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **errno** olarak **EINVAL** ve-1 döndürür.

Bu ve diğer hata kodları hakkında bilgi için bkz. [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**_Snprintf_s** işlevi, *arabellekte* *sayı* veya daha az karakter biçimlendirir ve bir Sonlandırıcı null değeri ekler. Her bağımsız değişken (varsa), karşılık *gelen biçim belirtimine* göre dönüştürülür ve çıktı. Biçimlendirme, **printf** işlev ailesiyle tutarlıdır; bkz. [Biçim belirtimi sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md). Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

*Sayı* [_TRUNCATE](../../c-runtime-library/truncate.md)ise, dizenin büyük bir süre sonunda null değer bırakarak *arabelleğe* sığacak şekilde **_snprintf_s** yazar. Tüm dize (null değeri sonlandırılıyor) *arabelleğe* sığıyorsa, **_snprintf_s** yazılan karakter sayısını döndürür (Sonlandırıcı null dahil değil); Aksi takdirde, **_snprintf_s** kesilmenin oluştuğunu belirtmek için-1 döndürür.

> [!IMPORTANT]
> *Biçimin* Kullanıcı tanımlı bir dize olmadığından emin olun.
>
>
> Windows 10 sürüm 2004 (derleme 19041) ' den başlayarak, `printf` işlev ailesi, yuvarlama IÇIN ıeee 754 kurallarına göre tam olarak gösterilemeyen kayan nokta numaralarını yazdırır. Önceki Windows sürümlerinde, ' 5 ' ile biten tam olarak gösterilemeyen kayan noktalı sayılar her zaman yukarı yuvarlar. IEEE 754, en yakın çift basamağa ("Banker ' de yuvarlama" olarak da bilinir) yuvarlayabilmeleri gerektiğini belirtir. Örneğin, her ikisi `printf("%1.0f", 1.5)` de `printf("%1.0f", 2.5)` 2 ' ye yuvarlanmalıdır. 1,5, daha önce 2,5 2 ' ye yuvarlayacağından, 3 ' e yuvarlanacak. Bu değişiklik yalnızca tam olarak gösterilebilir tablo numaralarını etkiler. Örneğin, 2,35 (bellekte temsil edildiğinde, 2.35000000000000008 'e yaklaşmışsa), 2,4 ' e yuvarlamaya devam eder. Bu işlevler tarafından yapılan yuvarlama artık tarafından ayarlanan kayan nokta yuvarlama moduna da uyar [`fesetround`](fegetround-fesetround2.md) . Daha önce, yuvarlama her zaman açık `FE_TONEAREST` davranış. Bu değişiklik yalnızca Visual Studio 2019 sürüm 16,2 ve üzeri kullanılarak oluşturulan programları etkiler. Eski kayan nokta yuvarlama davranışını kullanmak için [' legacy_stdio_float_rounding. obj '](../link-options.md)ile bağlantı yapın.

**_snwprintf_s** , **_snprintf_s** geniş karakterli bir sürümüdür; **_snwprintf_s** işaretçi bağımsız değişkenleri geniş karakterli dizelerdir. **_Snwprintf_s** kodlama hatalarının algılanması **_snprintf_s**' de farklılık gösterebilir. **swprintf_s** gibi **_Snwprintf_s**, çıktıyı **Dosya** türünde bir hedef yerine bir dizeye yazar.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

C++ ' da, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır) ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_sntprintf_s**|**_snprintf_s**|**_snprintf_s**|**_snwprintf_s**|
|**_sntprintf_s_l**|**_snprintf_s_l**|**_snprintf_s_l**|**_snwprintf_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_snprintf_s**, **_snprintf_s_l**|\<stdio.h>|
|**_snwprintf_s**, **_snwprintf_s_l**|\<stdio.h> veya \<wchar.h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```cpp
// crt_snprintf_s.cpp
// compile with: /MTd

// These #defines enable secure template overloads
// (see last part of Examples() below)
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES 1
#define _CRT_SECURE_CPP_OVERLOAD_STANDARD_NAMES_COUNT 1

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <crtdbg.h>  // For _CrtSetReportMode
#include <errno.h>

// This example uses a 10-byte destination buffer.

int snprintf_s_tester( const char * fmt, int x, size_t count )
{
   char dest[10];

   printf( "\n" );

   if ( count == _TRUNCATE )
      printf( "%zd-byte buffer; truncation semantics\n",
               _countof(dest) );
   else
      printf( "count = %zd; %zd-byte buffer\n",
               count, _countof(dest) );

   int ret = _snprintf_s( dest, _countof(dest), count, fmt, x );

   printf( "    new contents of dest: '%s'\n", dest );

   return ret;
}

void Examples()
{
   // formatted output string is 9 characters long: "<<<123>>>"
   snprintf_s_tester( "<<<%d>>>", 121, 8 );
   snprintf_s_tester( "<<<%d>>>", 121, 9 );
   snprintf_s_tester( "<<<%d>>>", 121, 10 );

   printf( "\nDestination buffer too small:\n" );

   snprintf_s_tester( "<<<%d>>>", 1221, 10 );

   printf( "\nTruncation examples:\n" );

   int ret = snprintf_s_tester( "<<<%d>>>", 1221, _TRUNCATE );
   printf( "    truncation %s occur\n", ret == -1 ? "did"
                                                  : "did not" );

   ret = snprintf_s_tester( "<<<%d>>>", 121, _TRUNCATE );
   printf( "    truncation %s occur\n", ret == -1 ? "did"
                                                  : "did not" );
   printf( "\nSecure template overload example:\n" );

   char dest[10];
   _snprintf( dest, 10, "<<<%d>>>", 12321 );
   // With secure template overloads enabled (see #defines
   // at top of file), the preceding line is replaced by
   //    _snprintf_s( dest, _countof(dest), 10, "<<<%d>>>", 12345 );
   // Instead of causing a buffer overrun, _snprintf_s invokes
   // the invalid parameter handler.
   // If secure template overloads were disabled, _snprintf would
   // write 10 characters and overrun the dest buffer.
   printf( "    new contents of dest: '%s'\n", dest );
}

void myInvalidParameterHandler(
   const wchar_t* expression,
   const wchar_t* function,
   const wchar_t* file,
   unsigned int line,
   uintptr_t pReserved)
{
   wprintf(L"Invalid parameter handler invoked: %s\n", expression);
}

int main( void )
{
   _invalid_parameter_handler oldHandler, newHandler;

   newHandler = myInvalidParameterHandler;
   oldHandler = _set_invalid_parameter_handler(newHandler);
   // Disable the message box for assertions.
   _CrtSetReportMode(_CRT_ASSERT, 0);

   Examples();
}
```

```Output

count = 8; 10-byte buffer
    new contents of dest: '<<<121>>'

count = 9; 10-byte buffer
    new contents of dest: '<<<121>>>'

count = 10; 10-byte buffer
    new contents of dest: '<<<121>>>'

Destination buffer too small:

count = 10; 10-byte buffer
Invalid parameter handler invoked: ("Buffer too small", 0)
    new contents of dest: ''

Truncation examples:

10-byte buffer; truncation semantics
    new contents of dest: '<<<1221>>'
    truncation did occur

10-byte buffer; truncation semantics
    new contents of dest: '<<<121>>>'
    truncation did not occur

Secure template overload example:
Invalid parameter handler invoked: ("Buffer too small", 0)
    new contents of dest: ''
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vprintf Işlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
