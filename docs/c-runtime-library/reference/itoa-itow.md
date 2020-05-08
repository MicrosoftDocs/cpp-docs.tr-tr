---
title: _itoa, _itow işlevleri
ms.date: 4/2/2020
api_name:
- itoa
- _itoa
- ltoa
- _ltoa
- ultoa
- _ultoa
- _i64toa
- _ui64toa
- _itow
- _ltow
- _ultow
- _i64tow
- _ui64tow
- _o__i64toa
- _o__i64tow
- _o__itoa
- _o__itow
- _o__ltoa
- _o__ltow
- _o__ui64toa
- _o__ui64tow
- _o__ultoa
- _o__ultow
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
- api-ms-win-crt-convert-l1-1-0.dll
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _itoa
- _ltoa
- _ultoa
- _i64toa
- _ui64toa
- _itow
- _ltow
- _ultow
- _i64tow
- _ui64tow
- itoa
- ltoa
- ultoa
- i64toa
- ui64toa
- itow
- ltow
- ultow
- i64tow
- ui64tow
- itot
- _itot
- ltot
- _ltot
- ultot
- _ultot
- i64tot
- _i64tot
- ui64tot
- _ui64tot
- _MAX_ITOSTR_BASE16_COUNT
- _MAX_ITOSTR_BASE10_COUNT
- _MAX_ITOSTR_BASE8_COUNT
- _MAX_ITOSTR_BASE2_COUNT
- _MAX_LTOSTR_BASE16_COUNT
- _MAX_LTOSTR_BASE10_COUNT
- _MAX_LTOSTR_BASE8_COUNT
- _MAX_LTOSTR_BASE2_COUNT
- _MAX_ULTOSTR_BASE16_COUNT
- _MAX_ULTOSTR_BASE10_COUNT
- _MAX_ULTOSTR_BASE8_COUNT
- _MAX_ULTOSTR_BASE2_COUNT
- _MAX_I64TOSTR_BASE16_COUNT
- _MAX_I64TOSTR_BASE10_COUNT
- _MAX_I64TOSTR_BASE8_COUNT
- _MAX_I64TOSTR_BASE2_COUNT
- _MAX_U64TOSTR_BASE16_COUNT
- _MAX_U64TOSTR_BASE10_COUNT
- _MAX_U64TOSTR_BASE8_COUNT
- _MAX_U64TOSTR_BASE2_COUNT
helpviewer_keywords:
- _itot function
- ui64toa function
- _ui64toa function
- converting integers
- itot function
- _i64tow function
- _i64toa function
- _itow function
- ui64tow function
- integers, converting
- itoa function
- _ui64tow function
- i64tow function
- itow function
- i64toa function
- converting numbers, to strings
- _itoa function
ms.assetid: 46592a00-77bb-4e73-98c0-bf629d96cea6
ms.openlocfilehash: 424ee4fb732811bffc6a83c0de57cd35fe747c42
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82914662"
---
# <a name="itoa-_itoa-ltoa-_ltoa-ultoa-_ultoa-_i64toa-_ui64toa-_itow-_ltow-_ultow-_i64tow-_ui64tow"></a>itoa, _itoa, ltoa, _ltoa, ultoa, _ultoa, _i64toa, _ui64toa, _itow, _ltow, _ultow, _i64tow, _ui64tow

Bir tamsayıyı bir dizeye dönüştürür. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [_itoa_s, _itow_s işlevleri](itoa-s-itow-s.md).

## <a name="syntax"></a>Sözdizimi

```C
char * _itoa( int value, char *buffer, int radix );
char * _ltoa( long value, char *buffer, int radix );
char * _ultoa( unsigned long value, char *buffer, int radix );
char * _i64toa( long long value, char *buffer, int radix );
char * _ui64toa( unsigned long long value, char *buffer, int radix );

wchar_t * _itow( int value, wchar_t *buffer, int radix );
wchar_t * _ltow( long value, wchar_t *buffer, int radix );
wchar_t * _ultow( unsigned long value, wchar_t *buffer, int radix );
wchar_t * _i64tow( long long value, wchar_t *buffer, int radix );
wchar_t * _ui64tow( unsigned long long value, wchar_t *buffer, int radix );

// These POSIX versions of the functions have deprecated names:
char * itoa( int value, char *buffer, int radix );
char * ltoa( long value, char *buffer, int radix );
char * ultoa( unsigned long value, char *buffer, int radix );

// The following template functions are C++ only:
template <size_t size>
char *_itoa( int value, char (&buffer)[size], int radix );

template <size_t size>
char *_itoa( long value, char (&buffer)[size], int radix );

template <size_t size>
char *_itoa( unsigned long value, char (&buffer)[size], int radix );

template <size_t size>
char *_i64toa( long long value, char (&buffer)[size], int radix );

template <size_t size>
char * _ui64toa( unsigned long long value, char (&buffer)[size], int radix );

template <size_t size>
wchar_t * _itow( int value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ltow( long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ultow( unsigned long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _i64tow( long long value, wchar_t (&buffer)[size], int radix );

template <size_t size>
wchar_t * _ui64tow( unsigned long long value, wchar_t (&buffer)[size],
   int radix );
```

### <a name="parameters"></a>Parametreler

*deeri*<br/>
Dönüştürülecek sayı.

*arabelleğin*<br/>
Dönüştürmenin sonucunu tutan arabellek.

*taban*<br/>
*Değer*dönüştürmesi için kullanılacak temel, 2-36 aralığında olmalıdır.

*boyutla*<br/>
Karakter türü birimlerde arabelleğin uzunluğu. Bu parametre, C++ içindeki *buffer* bağımsız değişkeninden algılanır.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, *arabelleğe*bir işaretçi döndürür. Hata döndürme yok.

## <a name="remarks"></a>Açıklamalar

**_İtoa**, **_ltoa**, **_ultoa**, **_i64toa**ve **_ui64toa** işlevleri verilen *değer* bağımsız değişkeninin basamaklarını null ile sonlandırılmış bir karakter dizesine **dönüştürür ve sonucu** **(_itoa ve** **_ltoa için**33 65 karaktere **kadar)** *arabelleğe*dönüştürür. **_ultoa** *Taban* eşittir 10 ve *değer* negatifse, depolanan dizenin ilk karakteri eksi işareti (**-**) olur. **_İtow**, **_ltow**, **_ultow**, **_i64tow**ve **_ui64tow** işlevleri sırasıyla **_itoa**, **_ltoa**, **_ultoa**, **_i64toa**ve **_ui64toa**geniş karakter sürümleridir.

> [!IMPORTANT]
> Bu işlevler, çok küçük bir arabellek sonunu geçmiş olabilir. Arabellek taşmalarını engellemek için, *arabelleğin* dönüştürülmüş rakamları ve sondaki null karakteri ve bir işaret karakterini tutabilecek kadar büyük olduğundan emin olun. Bu işlevlerin kötüye kullanılması, kodunuzda ciddi güvenlik sorunlarına neden olabilir.

Güvenlik sorunları nedeniyle bu işlevler, varsayılan olarak kullanımdan kaldırma Uyarısı [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)neden olur: **Bu işlev veya değişken güvenli olmayabilir. ** *safe_function* **Bunun yerine safe_function kullanmayı düşünün. Kullanımdan kaldırmayı devre dışı bırakmak için _CRT_SECURE_NO_WARNINGS kullanın.** Uyarı iletisi tarafından önerilen *safe_function* kullanmak için kaynak kodunuzu değiştirmenizi öneririz. Daha güvenli işlevler, belirtilen arabellek boyutundan daha fazla karakter yazamaz. Daha fazla bilgi için bkz. [_itoa_s, _itow_s işlevleri](itoa-s-itow-s.md).

Bu işlevleri kullanımdan kaldırma uyarısı olmadan kullanmak için, herhangi bir CRT üst bilgisi dahil etmeden önce **_CRT_SECURE_NO_WARNINGS** önişlemci makrosunu tanımlayın. Bunu, **CL** komutuna **/D_CRT_SECURE_NO_WARNINGS** derleyici seçeneğini ekleyerek bir geliştirici komut isteminde komut satırında yapabilirsiniz. Aksi takdirde, makroyu kaynak dosyalarınızda tanımlayın. Önceden derlenmiş üst bilgiler kullanıyorsanız, önceden derlenmiş üst bilgi dosyasının en üstünde, *pch. h* (Visual Studio 2017 ve önceki sürümlerde*stdadfx. h* ) dosyasını içeren makroyu tanımlayın. Kaynak kodunuzda makroyu tanımlamak için, bu örnekte olduğu gibi herhangi bir CRT başlığını eklemeden önce bir **#define** yönergesi kullanın:

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

C++ ' da, bu işlevlerde daha güvenli karşılıklarını çağıran şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

POSIX adları **itoa**, **ltoa**ve **ultoa** **_itoa**, **_ltoa**ve **_ultoa** işlevleri için diğer adlar olarak mevcuttur. POSIX adları, ISO C 'nin uygulamaya özgü genel işlev adı kurallarını takip ettiğinden kullanım dışıdır. Varsayılan olarak, bu işlevler kullanımdan kaldırma Uyarısı [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)neden olur: **Bu öğenin POSIX adı kullanım dışıdır. Bunun yerine, ISO C ve C++ uyumlu adı ' nı kullanın:** *new_name*. Bu işlevlerin daha güvenli sürümlerini kullanmak için kaynak kodunuzu değiştirmeniz önerilir **_itoa_s**, **_ltoa_s**veya **_ultoa_s**. Daha fazla bilgi için bkz. [_itoa_s, _itow_s işlevleri](itoa-s-itow-s.md).

Kaynak kodu taşınabilirliği için, kodunuzdaki POSIX adlarını tutmayı tercih edebilirsiniz. Bu işlevleri kullanımdan kaldırma uyarısı olmadan kullanmak için, herhangi bir CRT üst bilgisi dahil etmeden önce hem **_CRT_NONSTDC_NO_WARNINGS** hem de önişlemci makrolarını **_CRT_SECURE_NO_WARNINGS** tanımlayın. Bunu bir geliştirici komut isteminde komut satırında, **/D_CRT_SECURE_NO_WARNINGS** ve **/D_CRT_NONSTDC_NO_WARNINGS** derleyici seçeneklerini **CL** komutuna ekleyerek yapabilirsiniz. Aksi takdirde, kaynak dosyalarınızda makroları tanımlayın. Önceden derlenmiş üst bilgiler kullanırsanız, ön derlenmiş üst bilgi ekleme dosyasının en üstünde makroları tanımlayın. Kaynak kodunuzda makroları tanımlamak için, bu örnekte olduğu gibi herhangi bir CRT başlığını eklemeden önce **#define** yönergeleri kullanın:

```C
#define _CRT_NONSTDC_NO_WARNINGS 1
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

### <a name="maximum-conversion-count-macros"></a>En fazla dönüştürme sayısı makroları

Dönüşümler için güvenli arabellekler oluşturmanıza yardımcı olmak üzere CRT, bazı kullanışlı makrolar içerir. Bu, birkaç genel temel için null Sonlandırıcı ve işaret karakteri dahil olmak üzere her bir tamsayı türünün en uzun olası değerini dönüştürmek için gereken arabelleğin boyutunu tanımlar. Dönüştürme arabelleğinin *taban*tarafından belirtilen tabanda herhangi bir dönüştürmeyi alacak kadar büyük olduğundan emin olmak için, arabelleği ayırdığınızda bu tanımlı makrolardan birini kullanın. Bu, integral türlerini dizelere dönüştürürken arabellek taşma hatalarının önlenmesine yardımcı olur. Bu makrolar, kaynağınıza Stdlib. h veya WCHAR. h dahil edildiğinde tanımlanır.

Bir dize dönüştürme işlevinde, Bu makrolardan birini kullanmak için, uygun karakter türünün dönüştürme arabelleğini bildirin ve tamsayı türü için makro değerini ve arabellek boyutu olarak tabanı kullanın. Bu tabloda, listelenen temellere yönelik her bir işlev için uygun makrolar listelenmektedir:

||||
|-|-|-|
|İşlevler|taban|Makrolar|
|**_itoa**, **_itow**|16<br/>10<br/>8<br/>2|**_MAX_ITOSTR_BASE16_COUNT**<br/>**_MAX_ITOSTR_BASE10_COUNT**<br/>**_MAX_ITOSTR_BASE8_COUNT**<br/>**_MAX_ITOSTR_BASE2_COUNT**|
|**_ltoa**, **_ltow**|16<br/>10<br/>8<br/>2|**_MAX_LTOSTR_BASE16_COUNT**<br/>**_MAX_LTOSTR_BASE10_COUNT**<br/>**_MAX_LTOSTR_BASE8_COUNT**<br/>**_MAX_LTOSTR_BASE2_COUNT**|
|**_ultoa**, **_ultow**|16<br/>10<br/>8<br/>2|**_MAX_ULTOSTR_BASE16_COUNT**<br/>**_MAX_ULTOSTR_BASE10_COUNT**<br/>**_MAX_ULTOSTR_BASE8_COUNT**<br/>**_MAX_ULTOSTR_BASE2_COUNT**|
|**_i64toa**, **_i64tow**|16<br/>10<br/>8<br/>2|**_MAX_I64TOSTR_BASE16_COUNT**<br/>**_MAX_I64TOSTR_BASE10_COUNT**<br/>**_MAX_I64TOSTR_BASE8_COUNT**<br/>**_MAX_I64TOSTR_BASE2_COUNT**|
|**_ui64toa**, **_ui64tow**|16<br/>10<br/>8<br/>2|**_MAX_U64TOSTR_BASE16_COUNT**<br/>**_MAX_U64TOSTR_BASE10_COUNT**<br/>**_MAX_U64TOSTR_BASE8_COUNT**<br/>**_MAX_U64TOSTR_BASE2_COUNT**|

Bu örnek, taban 2 ' de **imzasız uzun uzun** bir süre içerecek büyüklükte bir arabellek tanımlamak için bir dönüştürme sayısı makrosu kullanır:

```cpp
#include <wchar.h>
#include <iostream>
int main()
{
    wchar_t buffer[_MAX_U64TOSTR_BASE2_COUNT];
    std:wcout << _ui64tow(0xFFFFFFFFFFFFFFFFull, buffer, 2) << std::endl;
}
```

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_itot**|**_itoa**|**_itoa**|**_itow**|
|**_ltot**|**_ltoa**|**_ltoa**|**_ltow**|
|**_ultot**|**_ultoa**|**_ultoa**|**_ultow**|
|**_i64tot**|**_i64toa**|**_i64toa**|**_i64tow**|
|**_ui64tot**|**_ui64toa**|**_ui64toa**|**_ui64tow**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**ıtoa**, **ltoa**, **ultoa**|\<Stdlib. h>|
|**_itoa**, **_ltoa**, **_ultoa**, **_i64toa**, **_ui64toa**|\<Stdlib. h>|
|**_itow**, **_ltow**, **_ultow**, **_i64tow**, **_ui64tow**|\<Stdlib. h> veya \<wchar. h>|

Bu işlevler ve makrolar, Microsoft 'a özgüdür. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu örnek, bazı tamsayı dönüştürme işlevlerinin kullanımını gösterir. Sessiz Uyarı C4996 için **_CRT_SECURE_NO_WARNINGS** makrosunun kullanımını dikkat edin.

```C
// crt_itoa.c
// Compile by using: cl /W4 crt_itoa.c
// This program makes use of the _itoa functions
// in various examples.

#define _CRT_SECURE_NO_WARNINGS 1
#include <stdio.h>      // for printf
#include <string.h>     // for strnlen
#include <stdlib.h>     // for _countof, _itoa fns, _MAX_COUNT macros

int main(void)
{
    char buffer[_MAX_U64TOSTR_BASE2_COUNT];
    int r;

    for (r = 10; r >= 2; --r)
    {
        _itoa(-1, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
    printf("\n");

    for (r = 10; r >= 2; --r)
    {
        _i64toa(-1LL, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
    printf("\n");

    for (r = 10; r >= 2; --r)
    {
        _ui64toa(0xffffffffffffffffULL, buffer, r);
        printf("base %d: %s (%d chars)\n", r, buffer,
            strnlen(buffer, _countof(buffer)));
    }
}
```

```Output
base 10: -1 (2 chars)
base 9: 12068657453 (11 chars)
base 8: 37777777777 (11 chars)
base 7: 211301422353 (12 chars)
base 6: 1550104015503 (13 chars)
base 5: 32244002423140 (14 chars)
base 4: 3333333333333333 (16 chars)
base 3: 102002022201221111210 (21 chars)
base 2: 11111111111111111111111111111111 (32 chars)

base 10: -1 (2 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)

base 10: 18446744073709551615 (20 chars)
base 9: 145808576354216723756 (21 chars)
base 8: 1777777777777777777777 (22 chars)
base 7: 45012021522523134134601 (23 chars)
base 6: 3520522010102100444244423 (25 chars)
base 5: 2214220303114400424121122430 (28 chars)
base 4: 33333333333333333333333333333333 (32 chars)
base 3: 11112220022122120101211020120210210211220 (41 chars)
base 2: 1111111111111111111111111111111111111111111111111111111111111111 (64 chars)
```

## <a name="see-also"></a>Ayrıca bkz.

[Veri dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_itoa_s, _itow_s işlevleri](itoa-s-itow-s.md)<br/>
