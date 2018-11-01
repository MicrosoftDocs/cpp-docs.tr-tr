---
title: _vcprintf, _vcprintf_l, _vcwprintf, _vcwprintf_l
ms.date: 11/04/2016
apiname:
- _vcwprintf
- _vcprintf_l
- _vcwprintf_l
- _vcprintf
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
apitype: DLLExport
f1_keywords:
- _vcwprintf_l
- _vtcprintf
- vcwprintf
- _vcwprintf
- vcprintf_l
- _vcprintf_l
- _vcprintf
- vcprintf
- vcwprintf_l
helpviewer_keywords:
- vcwprintf function
- _vcwprintf_l function
- _vcprintf function
- _vcprintf_l function
- vtcprintf_l function
- vcprintf function
- vcprintf_l function
- _vtcprintf function
- _vcwprintf function
- _vtcprintf_l function
- vcwprintf_l function
- vtcprintf function
- formatted text [C++]
ms.assetid: 4ef8d237-6200-4b66-8731-8c57e5624bb1
ms.openlocfilehash: e78d2f0b873042bda4fc79df100374b52751aebc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624763"
---
# <a name="vcprintf-vcprintfl-vcwprintf-vcwprintfl"></a>_vcprintf, _vcprintf_l, _vcwprintf, _vcwprintf_l

Bağımsız değişkenler listesine bir işaretçi kullanarak biçimlendirilmiş çıktı konsola yazar. Bu işlevlerin daha güvenli sürümleri mevcuttur, bkz [_vcprintf_s, _vcprintf_s_l, _vcwprintf_s, _vcwprintf_s_l](vcprintf-s-vcprintf-s-l-vcwprintf-s-vcwprintf-s-l.md).

> [!IMPORTANT]
> Bu API, Windows çalışma zamanı'nda yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için [Evrensel Windows platformu uygulamalarında desteklenmeyen CRT işlevleri](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _vcprintf(
   const char* format,
   va_list argptr
);
int _vcprintf_l(
   const char* format,
   locale_t locale,
   va_list argptr
);
int _vcwprintf(
   const wchar_t* format,
   va_list argptr
);
int _vcwprintf_l(
   const wchar_t* format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>Parametreler

*Biçim*<br/>
Biçim belirtimi.

*argptr*<br/>
Bağımsız değişkenler listesine işaretçi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için [biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

Yazılan karakter sayısını veya bir hata oluştuğunda negatif bir değer. Varsa *biçimi* null bir işaretçiyse, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve -1 döndürülür.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri bir bağımsız değişken listesi için bir işaretçi alır sonra biçimlendirir ve konsola verilen verileri yazar. **_vcwprintf** öğesinin geniş karakterli sürümüdür **_vcprintf**. İşlem, bir geniş karakter dizesi bağımsız değişken olarak alır.

Sahip bu işlevlerin sürümleri **_l** sonekine, geçerli yerel ayarı yerine iletilen yerel ayar parametresini kullanmalarıdır.

> [!IMPORTANT]
> Emin *biçimi* kullanıcı tanımlı bir dize değil. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtcprintf**|**_vcprintf**|**_vcprintf**|**_vcwprintf**|
|**_vtcprintf_l**|**_vcprintf_l**|**_vcprintf_l**|**_vcwprintf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üst bilgiler|
|-------------|---------------------|----------------------|
|**_vcprintf**, **_vcprintf_l**|\<conio.h > ve \<stdarg.h >|\<XENIX > *|
|**_vcwprintf**, **_vcwprintf_l**|\<conio.h > veya \<wchar.h >, ve \<stdarg.h >|\<XENIX > *|

\* UNIX V uyumluluğu için gerekli.

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```cpp
// crt_vcprintf.cpp
// compile with: /c
#include <conio.h>
#include <stdarg.h>

// An error formatting function used to print to the console.
int eprintf(const char* format, ...)
{
    va_list args;
    va_start(args, format);
    int result = _vcprintf(format, args);
    va_end(args);
    return result;
}

int main()
{
    eprintf("(%d:%d): Error %s%d : %s\n", 10, 23, "C", 2111,
           "<some error text>");
    eprintf("    (Related to symbol '%s' defined on line %d).\n",
            "<symbol>", 5 );
}
```

```Output
(10,23): Error C2111 : <some error text>
    (Related to symbol '<symbol>' defined on line 5).
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
