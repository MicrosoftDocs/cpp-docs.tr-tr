---
title: _itoa, _itow fonksiyonlar
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 0cc084076c5e39843ecc1afa08671ce6b2f06d1d
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342708"
---
# <a name="itoa-_itoa-ltoa-_ltoa-ultoa-_ultoa-_i64toa-_ui64toa-_itow-_ltow-_ultow-_i64tow-_ui64tow"></a>itoa, _itoa, ltoa, _ltoa, ultoa, _ultoa, _i64toa, _ui64toa, _itow, _ltow, _ultow, _i64tow, _ui64tow

Bir tamsayıyı dize dönüştürür. Bu işlevlerin daha güvenli sürümleri mevcuttur; [_itoa_s, _itow_s işlevleri](itoa-s-itow-s.md)görmek.

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

*Değer*<br/>
Dönüştürülecek numara.

*Arabellek*<br/>
Dönüştürme sonucunu tutan arabellek.

*Radix*<br/>
2-36 aralığında olması gereken *değerin*dönüştürülmesi için kullanılacak temel.

*Boyutu*<br/>
Karakter türündeki birimlerdeki arabellek uzunluğu. Bu parametre C++'daki *arabellek* bağımsız değişkeninden çıkarılır.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri *arabellek*için bir işaretçi döndürür. Hata iadesi yok.

## <a name="remarks"></a>Açıklamalar

**_itoa**, **_ltoa**, **_ultoa**, **_i64toa**, ve **_ui64toa** işlevleri verilen *değer* argümanının basamaklarını null-sonlandırılan bir karakter dizesine dönüştürür ve sonucu **(_itoa**için 33 karaktere kadar , **_ltoa**ve **_ultoa**, **_i64toa** ve **_ui64toa**için 65 ) *arabellekte*saklar. *Radix* 10'a eşitse ve *değer* negatifse, depolanan dizenin ilk karakteri eksi işaretidir (**-**). **_itow**, **_ltow**, **_ultow**, **_i64tow**, ve **_ui64tow** işlevleri **_itoa**geniş karakter sürümleri , **_ltoa**, **_ultoa**, **_i64toa**, ve **_ui64toa**, sırasıyla.

> [!IMPORTANT]
> Bu işlevler, çok küçük bir arabelleğe geçmiş yazabilirsiniz. Arabellek taşmaları önlemek için *arabellek* dönüştürülen basamakartı sondaki null-karakter ve bir işaret karakteri tutmak için yeterince büyük olduğundan emin olun. Bu işlevlerin kötüye kullanılması, kodunuzda ciddi güvenlik sorunlarına neden olabilir.

Güvenlik sorunları için potansiyelnedeniyle, varsayılan olarak, bu işlevler [c4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)amortisman uyarısı neden : **Bu işlev veya değişken güvenli olmayabilir. ** *Bunun* yerine safe_function kullanmayı **düşünün. Amortismanı devre dışı kalmak için _CRT_SECURE_NO_WARNINGS kullanın.** Uyarı iletisinin önerdiği *safe_function* kullanmak için kaynak kodunuzu değiştirmenizi öneririz. Daha güvenli işlevler belirtilen arabellek boyutundan daha fazla karakter yazmaz. Daha fazla bilgi için [_itoa_s _itow_s işlevlerine](itoa-s-itow-s.md)bakın.

Bu işlevleri amortisman uyarısı olmadan kullanmak için, crt üstbilgileri dahil etmeden önce **_CRT_SECURE_NO_WARNINGS** önişlemci makrosu tanımlayın. Bunu bir geliştirici komut istemindeki komut satırında **cl** komutuna **/D_CRT_SECURE_NO_WARNINGS** derleyici seçeneğini ekleyerek yapabilirsiniz. Aksi takdirde, kaynak dosyalarınızdaki makroyu tanımlayın. Önceden derlenmiş üstbilgi kullanıyorsanız, önceden derlenen üstbilginin üst kısmındaki makroyu tanımlayın dosya, *pch.h* (Visual Studio 2017 ve öncesi*stdafx.h).* Kaynak kodunuzdaki makroyu tanımlamak için, bu örnekte olduğu gibi herhangi bir CRT üstbilgisini eklemeden önce **bir #define** yönergesi kullanın:

```C
By default, this function's global state is scoped to the application. To change this, see [Global state in the CRT](../global-state.md).

#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

C++'da, bu işlevler daha güvenli karşılıklarını çağıran şablon aşırı yüklemelerine sahiptir. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

POSIX isimleri **itoa**, **ltoa**, ve **ultoa** **_itoa**için takma olarak var , **_ltoa**, ve **_ultoa** işlevleri. POSIX adları, ISO C'nin uygulamaya özgü global işlev adı kurallarına uymadıkları için amortismana alınır. Varsayılan olarak, bu işlevler amortisman uyarısı [C4996](../../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md)neden : **Bu öğenin POSIX adı amortismana. Bunun yerine, ISO C ve C++ konforyan adını kullanın:** *new_name.* Kaynak kodunuzu bu işlevlerin, **_itoa_s,** **_ltoa_s**veya **_ultoa_s**daha güvenli sürümlerini kullanmak için değiştirmenizi öneririz. Daha fazla bilgi için [_itoa_s _itow_s işlevlerine](itoa-s-itow-s.md)bakın.

Kaynak kodu taşınabilirliği için, kodunuzda POSIX adlarını saklamayı tercih edebilirsiniz. Bu işlevleri amortisman uyarısı olmadan kullanmak için, crt üstbilgileri dahil etmeden önce hem **_CRT_NONSTDC_NO_WARNINGS** hem de **_CRT_SECURE_NO_WARNINGS** önişlemci makrolarını tanımlayın. Bunu bir geliştirici komut istemindeki komut satırında **cl** komutuna **/D_CRT_SECURE_NO_WARNINGS** ve **/D_CRT_NONSTDC_NO_WARNINGS** derleyici seçeneklerini ekleyerek yapabilirsiniz. Aksi takdirde, kaynak dosyalarınızdaki makroları tanımlayın. Önceden derlenmiş üstbilgi kullanıyorsanız, önceden derlenmiş üstbilginin üst kısmındaki makroları tanımlayın dosyayı ekleyin. Kaynak kodunuzdaki makroları tanımlamak için, bu örnekte olduğu gibi herhangi bir CRT üstbilgisini eklemeden önce **#define** yönergelerini kullanın:

```C
#define _CRT_NONSTDC_NO_WARNINGS 1
#define _CRT_SECURE_NO_WARNINGS 1
#include <stdlib.h>
```

### <a name="maximum-conversion-count-macros"></a>Maksimum dönüşüm sayısı makroları

Dönüşümler için güvenli arabellek oluşturmanıza yardımcı olmak için CRT bazı kullanışlı makrolar içerir. Bunlar, birkaç ortak taban için null sonlandırıcı ve işaret karakteri de dahil olmak üzere her bir insa türündeki olası en uzun değeri dönüştürmek için gereken arabelleğe boyutunu tanımlar. Dönüştürme *arabellizinradix*tarafından belirtilen tabanda herhangi bir dönüşüm alacak kadar büyük olduğundan emin olmak için, arabelleği ayırırken bu tanımlanmış makrolardan birini kullanın. Bu, integral türlerini dizeleri dönüştürdüğünüzde arabellek taşma hatalarını önlemeye yardımcı olur. Bu makrolar, kaynağınıza stdlib.h veya wchar.h eklediğinizde tanımlanır.

Dize dönüştürme işlevinde bu makrolardan birini kullanmak için, dönüşüm arabelleğe uygun karakter türüne bildirin ve arabellek boyutu olarak tamsayı türü ve tabanı için makro değerini kullanın. Bu tablo, listelenen üsler için her işlev için uygun makroları listeler:

||||
|-|-|-|
|İşlevler|Radix|Makrolar|
|**_itoa**, **_itow**|16<br/>10<br/>8<br/>2|**_MAX_ITOSTR_BASE16_COUNT**<br/>**_MAX_ITOSTR_BASE10_COUNT**<br/>**_MAX_ITOSTR_BASE8_COUNT**<br/>**_MAX_ITOSTR_BASE2_COUNT**|
|**_ltoa**, **_ltow**|16<br/>10<br/>8<br/>2|**_MAX_LTOSTR_BASE16_COUNT**<br/>**_MAX_LTOSTR_BASE10_COUNT**<br/>**_MAX_LTOSTR_BASE8_COUNT**<br/>**_MAX_LTOSTR_BASE2_COUNT**|
|**_ultoa**, **_ultow**|16<br/>10<br/>8<br/>2|**_MAX_ULTOSTR_BASE16_COUNT**<br/>**_MAX_ULTOSTR_BASE10_COUNT**<br/>**_MAX_ULTOSTR_BASE8_COUNT**<br/>**_MAX_ULTOSTR_BASE2_COUNT**|
|**_i64toa**, **_i64tow**|16<br/>10<br/>8<br/>2|**_MAX_I64TOSTR_BASE16_COUNT**<br/>**_MAX_I64TOSTR_BASE10_COUNT**<br/>**_MAX_I64TOSTR_BASE8_COUNT**<br/>**_MAX_I64TOSTR_BASE2_COUNT**|
|**_ui64toa**, **_ui64tow**|16<br/>10<br/>8<br/>2|**_MAX_U64TOSTR_BASE16_COUNT**<br/>**_MAX_U64TOSTR_BASE10_COUNT**<br/>**_MAX_U64TOSTR_BASE8_COUNT**<br/>**_MAX_U64TOSTR_BASE2_COUNT**|

Bu örnek, temel **2'de imzasız uzun** bir uzun içeren yeterince büyük bir arabellek tanımlamak için bir dönüşüm sayımı makrosu kullanır:

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
|**itoa**, **ltoa**, **ultoa**|\<stdlib.h>|
|**_itoa**, **_ltoa**, **_ultoa**, **_i64toa**, **_ui64toa**|\<stdlib.h>|
|**_itow**, **_ltow**, **_ultow**, **_i64tow**, **_ui64tow**|\<stdlib.h> \<veya wchar.h>|

Bu işlevler ve makrolar Microsoft'a özgür. Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

## <a name="example"></a>Örnek

Bu örnek, bazı tamsayı dönüştürme işlevlerinin kullanımını gösterir. Uyarı C4996 sessizlik **için _CRT_SECURE_NO_WARNINGS** makro kullanımı unutmayın.

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
[_itoa_s, _itow_s fonksiyonlar](itoa-s-itow-s.md)<br/>
