---
title: _itoa, _itow işlevleri
ms.date: 03/21/2018
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
- ntoskrnl.exe
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
ms.openlocfilehash: 016f3474345b623415be9fe33556bb9f466542ad
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62157376"
---
# <a name="itoa-itoa-ltoa-ltoa-ultoa-ultoa-i64toa-ui64toa-itow-ltow-ultow-i64tow-ui64tow"></a>itoa, _itoa, ltoa, _ltoa, ultoa, _ultoa, _i64toa, _ui64toa, _itow, _ltow, _ultow, _i64tow, _ui64tow

Bir tamsayı, bir dizeye dönüştürür. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [_itoa_s, _itow_s işlevleri](itoa-s-itow-s.md).

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
Dönüştürme sonucunu tutacak arabelleği.

*radix*<br/>
Dönüştürme için kullanılacak temel *değer*, 2-36 aralığında olması gerekir.

*Boyutu*<br/>
Karakter türü birimlik arabellek uzunluğu. Bu parametre içinden gösterilen *arabellek* c++ bağımsız değişken.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri işaretçi döndürür *arabellek*. Döndürülen hata yok.

## <a name="remarks"></a>Açıklamalar

**_İtoa**, **_ltoa**, **_ultoa**, **_i64toa**, ve **_ui64toa** işlevleri rakamı Dönüştür verilen *değer* bağımsız değişkeni null ile sonlandırılmış dize ve sonuç deposu (en fazla 33 karakterleri **_itoa**, **_ltoa**, ve  **_ultoa**ve 65 için **_i64toa** ve **_ui64toa**) içinde *arabellek*. Varsa *taban* 10 eşittir ve *değer* olan negatif saklı dizenin ilk karakteri eksi işareti olan (**-**). **_İtow**, **_ltow**, **_ultow**, **_i64tow**, ve **_ui64tow** geniş karakter işlevleri sürümleri **_itoa**, **_ltoa**, **_ultoa**, **_i64toa**, ve **_ui64toa**, sırasıyla.

> [!IMPORTANT]
> Bu işlevler, çok küçük bir arabellek sonunun yazabilirsiniz. Arabellek Taşması önlemek için emin olun *arabellek* dönüştürülmüş basamakların yanı sıra sondaki null karakteri ve işaret karakterinin tutabilecek kadar büyük olduğundan. Bu işlevlerin kötüye kodunuzda ciddi güvenlik sorunlarına neden olabilir.

Bu işlevler, potansiyellerini varsayılan olarak, güvenlik sorunları nedeniyle kullanımdan kaldırılma uyarısı neden [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md): **Bu işlev veya değişken güvenli olmayabilir. Kullanmayı** *safe_function* **yerine. Kullanımdan kaldırma devre dışı bırakmak için _crt_secure_no_warnıngs kullanın.** Kullanılacak kaynak kodunuzu değiştirmeniz önerilir *safe_function* uyarı iletisi tarafından önerilen. Belirtilen arabellek boyutu daha fazla karakterden daha güvenli işlevler yazma. Daha fazla bilgi için [_itoa_s, _itow_s işlevleri](itoa-s-itow-s.md).

Kullanımdan kaldırılma uyarısı olmadan bu işlevler için tanımladığınız **_crt_secure_no_warnıngs** CRT üst bilgileri de dahil olmak üzere önce önişlemci makrosu. Komut satırında bir geliştirici komut istemi ekleyerek bunu yapabilirsiniz **/D_CRT_SECURE_NO_WARNINGS** derleyici seçeneği **cl** komutu. Aksi takdirde, kaynak dosyalarınızda makro tanımlayın. Önceden derlenmiş üstbilgileri kullanmak, önceden derlenmiş üst bilgi üst kısmındaki makro tanımlayın. genellikle stdafx.h dosyası bulunur. Kaynak kodunuzu makro tanımlamak için bir **#define** Bu örnekte olduğu gibi herhangi bir CRT başlığını dahil etmeden önce yönergesi:

```C
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

C++'da, bu işlevlerin daha güvenli karşılıkları çağırma şablon aşırı yüklemeleri vardır. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

POSIX adları **itoa**, **ltoa**, ve **ultoa** için diğer ad olarak mevcut **_itoa**, **_ltoa**, ve **_ultoa** işlevleri. ISO c uygulamaya özel işlev adı kurallarını izlemeyin çünkü POSIX adları kullanım dışıdır Varsayılan olarak, bu işlevler, kullanımdan kaldırılma uyarısı neden [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md): **Bu öğe için POSIX ad kullanım dışı bırakılmıştır. Bunun yerine ISO C kullanın ve C++ uyumluluğunu adı:** *new_name*. Bu işlevlerin daha güvenli sürümleri kullanmak için kaynak kodunuzu değiştirmeniz önerilir **_itoa_s**, **_ltoa_s**, veya **_ultoa_s**. Daha fazla bilgi için [_itoa_s, _itow_s işlevleri](itoa-s-itow-s.md).

Kaynak kodu taşınabilirlik için kodunuzda POSIX adlarını korumak isteyebilirsiniz. Bu işlevler kullanımdan kaldırılma uyarısı olmadan kullanmak için her ikisi de tanımlamak **_CRT_NONSTDC_NO_WARNINGS** ve **_crt_secure_no_warnıngs** Önişlemci makroları CRT üst bilgileri de dahil olmak üzere önce. Komut satırında bir geliştirici komut istemi ekleyerek bunu yapabilirsiniz **/D_CRT_SECURE_NO_WARNINGS** ve **/D_CRT_NONSTDC_NO_WARNINGS** derleyici seçenekleri için **cl**komutu. Aksi takdirde, kaynak dosyalarınızda makroları tanımlar. Önceden derlenmiş üstbilgileri kullanmak, tanımlama dosyası, genellikle stdafx.h önceden derlenmiş üst bilgi üst kısmındaki makrolar şunlardır. Kaynak kodunuzu makroları tanımlamak için **#define** Bu örnekte olduğu gibi herhangi bir CRT başlığını dahil etmeden önce yönergeleri:

```C
#define _CRT_NONSTDC_NO_WARNINGS 1
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

### <a name="maximum-conversion-count-macros"></a>En fazla dönüşüme sayısı makroları

Dönüştürmeler için güvenli arabellek oluşturmanıza yardımcı olacak bazı kullanışlı makroları CRT içerir. Bu null Sonlandırıcı dahil olmak üzere, her bir tamsayı türü olası en uzun değerini dönüştürmek için gerekli arabellek boyutu tanımlayın ve karakter, birkaç ortak temelleri için oturum açın. Dönüştürme arabelleğin herhangi bir dönüştürmeyi tarafından belirtilen tabanda almak büyük olduğundan emin olmak için *taban*, bunlardan birini tanımlı makroları olduğunda arabelleği ayrılamadı. Bu, tam sayı türleri için dizeleri dönüştürdüğünüzde, arabellek taşma hataları önlemeye yardımcı olur. Kaynağınızda stdlıb.h veya wchar.h eklediğinizde bu makrolar tanımlanır.

Bu makrolar bir dize dönüştürme işlevini kullanmak için uygun bir karakter türü dönüştürme arabelleğin bildirme ve makrosu değeri tamsayı türü ve temel için arabellek boyutu olarak kullanın. Bu tablo, her işlevin listelenen temelleri için uygun olan makroları listeler:

||||
|-|-|-|
|İşlevler|sayı tabanı|Makrolar|
|**_itoa**, **_itow**|16<br/>10<br/>8<br/>2|**_MAX_ITOSTR_BASE16_COUNT**<br/>**_MAX_ITOSTR_BASE10_COUNT**<br/>**_MAX_ITOSTR_BASE8_COUNT**<br/>**_MAX_ITOSTR_BASE2_COUNT**|
|**_ltoa**, **_ltow**|16<br/>10<br/>8<br/>2|**_MAX_LTOSTR_BASE16_COUNT**<br/>**_MAX_LTOSTR_BASE10_COUNT**<br/>**_MAX_LTOSTR_BASE8_COUNT**<br/>**_MAX_LTOSTR_BASE2_COUNT**|
|**_ultoa**, **_ultow**|16<br/>10<br/>8<br/>2|**_MAX_ULTOSTR_BASE16_COUNT**<br/>**_MAX_ULTOSTR_BASE10_COUNT**<br/>**_MAX_ULTOSTR_BASE8_COUNT**<br/>**_MAX_ULTOSTR_BASE2_COUNT**|
|**_i64toa**, **_i64tow**|16<br/>10<br/>8<br/>2|**_MAX_I64TOSTR_BASE16_COUNT**<br/>**_MAX_I64TOSTR_BASE10_COUNT**<br/>**_MAX_I64TOSTR_BASE8_COUNT**<br/>**_MAX_I64TOSTR_BASE2_COUNT**|
|**_ui64toa**, **_ui64tow**|16<br/>10<br/>8<br/>2|**_MAX_U64TOSTR_BASE16_COUNT**<br/>**_MAX_U64TOSTR_BASE10_COUNT**<br/>**_MAX_U64TOSTR_BASE8_COUNT**<br/>**_MAX_U64TOSTR_BASE2_COUNT**|

Bu örnek bir dönüştürme sayısı makrosu içerecek şekilde büyük bir arabellek tanımlamak için kullanır. bir **işaretsiz long long** taban 2'de:

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
|**itoa**, **ltoa**, **ultoa**|\<stdlib.h >|
|**_itoa**, **_ltoa**, **_ultoa**, **_i64toa**, **_ui64toa**|\<stdlib.h >|
|**_itow**, **_ltow**, **_ultow**, **_i64tow**, **_ui64tow**|\<stdlib.h > veya \<wchar.h >|

Bu işlevlerle makrolar Microsoft özgüdür. Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

Bu örnek, tamsayı dönüştürme işlevleri bazıları kullanımını gösterir. Kullanımına dikkat edin **_crt_secure_no_warnıngs** uyarı C4996 sessiz makrosu.

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

[Veri Dönüştürme](../../c-runtime-library/data-conversion.md)<br/>
[_itoa_s, _itow_s işlevleri](itoa-s-itow-s.md)<br/>
