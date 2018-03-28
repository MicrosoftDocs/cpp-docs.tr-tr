---
title: _itoa, _itow işlevleri | Microsoft Docs
ms.custom: ''
ms.date: 03/21/2018
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0a471e0df86dbfd5e8c267c463684a088b400863
ms.sourcegitcommit: 604907f77eb6c5b1899194a9877726f3e8c2dabc
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/28/2018
---
# <a name="itoa-itoa-ltoa-ltoa-ultoa-ultoa-i64toa-ui64toa-itow-ltow-ultow-i64tow-ui64tow"></a>itoa, _itoa, ltoa, _ltoa, ultoa, _ultoa, _i64toa, _ui64toa, _itow, _ltow, _ultow, _i64tow, _ui64tow

Tamsayı bir dizeye dönüştürür. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_itoa_s, _itow_s işlevler](../../c-runtime-library/reference/itoa-s-itow-s.md).

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

// These Posix versions of the functions have deprecated names:
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

*value*<br/>
Dönüştürülecek sayı.

*Arabellek*<br/>
Dönüştürme işleminin sonucu tutan bir arabellek.

*radix*<br/>
Dönüştürme işlemi için kullanılacak olan temeli *değeri*, 2-36 aralığında olmalıdır.

*Boyutu*<br/>
Karakter türü birimlerinde arabellek uzunluğu. Bu parametre gelen çıkarımı yapılan *arabellek* C++ bağımsız değişkeni.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri için bir işaretçi döndürür *arabellek*. Döndürülen hata yoktur.

## <a name="remarks"></a>Açıklamalar

`_itoa`, `_ltoa`, `_ultoa`, `_i64toa`, Ve `_ui64toa` işlevleri Dönüştür rakamı verilen *değeri* bağımsız değişkeni null olarak sonlandırılan bir karakter dizesi ve (kadar 33 sonuç deposu için karakter `_itoa`, `_ltoa`, ve `_ultoa`ve 65 için `_i64toa` ve `_ui64toa`) içinde *arabellek*. Varsa *taban* eşittir 10 ve *değeri* olan negatif saklı dizenin ilk karakter eksi işareti'dir (**-**). `_itow`, `_ltow`, `_ultow`, `_i64tow`, Ve `_ui64tow` işlevlerdir joker karakter sürümlerini `_itoa`, `_ltoa`, `_ultoa`, `_i64toa`, ve `_ui64toa`sırasıyla.

> [!IMPORTANT]
> Bu işlevler çok küçük bir arabellek sonunun yazabilirsiniz. Arabellek aşırı çalıştırmaları önlemek için emin *arabellek* dönüştürülmüş basamak artı sonunda null karakteri ve bir oturum karakter tutmak için büyük. Bu işlevlerin kötüye önemli güvenlik sorunları kodunuzda neden olabilir.

Kendi olası varsayılan olarak, güvenlik sorunları nedeniyle bu işlevler kullanımdan kaldırma uyarısı neden [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md): **bu işlev veya değişken güvenli olmayabilir. Kullanmayı** *safe_function* **yerine. Kullanımdan kaldırma devre dışı bırakmak için _CRT_SECURE_NO_WARNINGS kullanın.** Kullanmak için kaynak kodunuzu değiştirmek öneririz *safe_function* uyarı iletisi tarafından önerilen. Belirtilen arabellek boyutu daha fazla karakterden daha güvenli işlevler yazma. Daha fazla bilgi için bkz: [_itoa_s, _itow_s işlevler](../../c-runtime-library/reference/itoa-s-itow-s.md).

Kullanımdan kaldırma uyarısı olmadan bu işlevleri kullanmak için tanımlamanız **_CRT_SECURE_NO_WARNINGS** tüm CRT üstbilgileri eklemeden önce önişlemci makrosu. Bir geliştirici komut istemi komut satırında ekleyerek bunu yapabilirsiniz **/D_CRT_SECURE_NO_WARNINGS** derleyici seçeneği **cl** komutu. Aksi halde, Kaynak dosyalarınız makrosu tanımlayın. Önceden derlenmiş üstbilgiler kullanırsanız, önceden derlenmiş üst bilgi üstündeki makrosu tanımlama dosyası, genellikle stdafx.h içerir. Kaynak kodunuz makrosu tanımlamak için bir **#define** Bu örnekte olduğu gibi herhangi bir CRT başlığını dahil etmeden önce yönergesi:

```C
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

C++'da, bu işlevler daha güvenli dekiler çağırma şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

POSIX adlarını `itoa`, `ltoa`, ve `ultoa` için diğer adlar mevcut `_itoa`, `_ltoa`, ve `_ultoa` işlevleri. ISO C. uygulamaya özel işlevi adı kuralları izlemeyin çünkü POSIX adlarını kullanım dışı bırakılmıştır Varsayılan olarak, bu işlevler kullanımdan kaldırma uyarısı neden [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md): **POSIX adı bu öğe için kullanım dışıdır. Bunun yerine, ISO C ve C++ uyumluluğunu adını kullanın:** *new_name*. Bu işlevlerin güvenli sürümlerini kullanmak için kaynak kodunuzu değiştirmek öneririz `_itoa_s`, `_ltoa_s`, veya `_ultoa_s`. Daha fazla bilgi için bkz: [_itoa_s, _itow_s işlevler](../../c-runtime-library/reference/itoa-s-itow-s.md).

Kaynak kodu taşınabilirlik için kodunuzu POSIX adlarında korumak tercih edebilirsiniz. Kullanımdan kaldırma uyarısı olmadan bu işlevleri kullanmak için her ikisi de tanımlamak **_CRT_NONSTDC_NO_WARNINGS** ve **_CRT_SECURE_NO_WARNINGS** tüm CRT üstbilgileri eklemeden önce Önişlemci makroları. Bir geliştirici komut istemi komut satırında ekleyerek bunu yapabilirsiniz **/D_CRT_SECURE_NO_WARNINGS** ve **/D_CRT_NONSTDC_NO_WARNINGS** derleyici seçenekleri için **cl**komutu. Aksi halde, Kaynak dosyalarınız makrolar tanımlayın. Önceden derlenmiş üstbilgiler kullanırsanız, tanımlama dosyası, genellikle stdafx.h önceden derlenmiş üst bilgi üstündeki makrolar şunlardır. Kaynak kodunuz makrolar tanımlamak için **#define** Bu örnekte olduğu gibi herhangi bir CRT başlığını dahil etmeden önce yönergeleri:

```C
#define _CRT_NONSTDC_NO_WARNINGS 1
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

### <a name="maximum-conversion-count-macros"></a>En fazla dönüştürme sayısı makroları

Dönüştürmeleri için güvenli arabellekleri oluşturmanıza yardımcı olması için bazı kullanışlı makrolar CRT içerir. Bu en uzun olası değeri null Sonlandırıcı dahil olmak üzere her Tamsayı türünde dönüştürmek için gerekli olan arabellek boyutunu tanımlamak ve birkaç ortak temelleri için karakter imzalayın. Dönüştürme arabellek tarafından belirtilen Base herhangi bir dönüştürmeye almak için yeterince büyük olduğundan emin olmak için *taban*, bunlardan birini tanımlı makrolar arabellek ayıramadı olduğunda. Bu, tam sayı türleri dizelere dönüştürürken arabellek taşması hataları önlemeye yardımcı olur. Kaynak stdlib.h veya wchar.h eklediğinizde bu makroları tanımlanır.

Dize dönüştürme işlevinde bu makroları birini kullanmak için uygun karakter türü, dönüştürme arabelleği bildirme ve makrosu değeri tamsayı türü ve temel için arabellek boyutu olarak kullanın. Bu tablo her işlevi listelenen temelleri için uygun olan makroları listelenmektedir:

||||
|-|-|-|
|İşlevler|sayı tabanını|Makrolar|
|`_itoa`, `_itow`|16<br/>10<br/>8<br/>2|`_MAX_ITOSTR_BASE16_COUNT`<br/>`_MAX_ITOSTR_BASE10_COUNT`<br/>`_MAX_ITOSTR_BASE8_COUNT`<br/>`_MAX_ITOSTR_BASE2_COUNT`|
|`_ltoa`, `_ltow`|16<br/>10<br/>8<br/>2|`_MAX_LTOSTR_BASE16_COUNT`<br/>`_MAX_LTOSTR_BASE10_COUNT`<br/>`_MAX_LTOSTR_BASE8_COUNT`<br/>`_MAX_LTOSTR_BASE2_COUNT`|
|`_ultoa`, `_ultow`|16<br/>10<br/>8<br/>2|`_MAX_ULTOSTR_BASE16_COUNT`<br/>`_MAX_ULTOSTR_BASE10_COUNT`<br/>`_MAX_ULTOSTR_BASE8_COUNT`<br/>`_MAX_ULTOSTR_BASE2_COUNT`|
|`_i64toa`, `_i64tow`|16<br/>10<br/>8<br/>2|`_MAX_I64TOSTR_BASE16_COUNT`<br/>`_MAX_I64TOSTR_BASE10_COUNT`<br/>`_MAX_I64TOSTR_BASE8_COUNT`<br/>`_MAX_I64TOSTR_BASE2_COUNT`|
|`_ui64toa`, `_ui64tow`|16<br/>10<br/>8<br/>2|`_MAX_U64TOSTR_BASE16_COUNT`<br/>`_MAX_U64TOSTR_BASE10_COUNT`<br/>`_MAX_U64TOSTR_BASE8_COUNT`<br/>`_MAX_U64TOSTR_BASE2_COUNT`|

Bu örnek bir dönüştürme sayısı makro alabilecek kadar büyük bir arabellek tanımlamak için kullanır. bir **uzun uzun imzasız** temel 2:

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
|`_itot`|`_itoa`|`_itoa`|`_itow`|
|`_ltot`|`_ltoa`|`_ltoa`|`_ltow`|
|`_ultot`|`_ultoa`|`_ultoa`|`_ultow`|
|`_i64tot`|`_i64toa`|`_i64toa`|`_i64tow`|
|`_ui64tot`|`_ui64toa`|`_ui64toa`|`_ui64tow`|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|`itoa`, `ltoa`, `ultoa`|\<stdlib.h>|
|`_itoa`, `_ltoa`, `_ultoa`, `_i64toa`, `_ui64toa`|\<stdlib.h>|
|`_itow`, `_ltow`, `_ultow`, `_i64tow`, `_ui64tow`|\<stdlib.h > veya \<wchar.h >|

Bu işlevler ve makrolar Microsoft özgüdür. Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu örnek bazı tamsayı dönüştürme işlevleri kullanımını göstermektedir. Kullanımına dikkat edin **_CRT_SECURE_NO_WARNINGS** uyarı C4996 sessiz makrosu.

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

## <a name="see-also"></a>Ayrıca Bkz.

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_itoa_s, _itow_s işlevleri](../../c-runtime-library/reference/itoa-s-itow-s.md)<br/>
