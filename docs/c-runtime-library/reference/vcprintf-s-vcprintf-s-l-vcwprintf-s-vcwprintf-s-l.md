---
description: 'Hakkında daha fazla bilgi edinin: _vcprintf_s, _vcprintf_s_l, _vcwprintf_s, _vcwprintf_s_l'
title: _vcprintf_s, _vcprintf_s_l, _vcwprintf_s, _vcwprintf_s_l
ms.date: 3/9/2021
api_name:
- _vcprintf_s
- _vcprintf_s_l
- _vcwprintf_s
- _vcwprintf_s_l
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
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- vcprintf_s
- vcwprintf_s_l
- _vcwprintf_s
- _vcwprintf_s_l
- _vcprintf_s_l
- _vtcprintf_s
- vcwprintf_s
- vcprintf_s_l
- _vcprintf_s
helpviewer_keywords:
- _vtcprintf_s_l function
- _vcwprintf_s_l function
- _vtcprintf_s function
- vtcprintf_s_l function
- vcprintf_s_l function
- _vcprintf_s function
- _vcwprintf_s function
- vcwprintf_s_l function
- vcwprintf_s function
- vcprintf_s function
- _vcprintf_s_l function
- vtcprintf_s function
- formatted text [C++]
ms.openlocfilehash: 1b427d0e56d6d1866f72d101e3f7c2c3562d3d42
ms.sourcegitcommit: b04b39940b0c1e265f80fc1951278fdb05a1b30a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102621508"
---
# <a name="_vcprintf_s-_vcprintf_s_l-_vcwprintf_s-_vcwprintf_s_l"></a>_vcprintf_s, _vcprintf_s_l, _vcwprintf_s, _vcwprintf_s_l

Bağımsız değişken listesine yönelik bir işaretçi kullanarak konsola biçimli çıktıyı yazar. [_Vcprintf, _vcprintf_l, _vcwprintf _vcwprintf_l](vcprintf-vcprintf-l-vcwprintf-vcwprintf-l.md) bu SÜRÜMLERINDE, [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri vardır.

> [!IMPORTANT]
> Bu API, Windows Çalışma Zamanı yürütülen uygulamalarda kullanılamaz. Daha fazla bilgi için bkz. [Evrensel Windows platformu uygulamalarında CRT işlevleri desteklenmez](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Sözdizimi

```C
int _vcprintf(
   const char* format,
   va_list argptr
);
int _vcprintf(
   const char* format,
   locale_t locale,
   va_list argptr
);
int _vcwprintf_s(
   const wchar_t* format,
   va_list argptr
);
int _vcwprintf_s_l(
   const wchar_t* format,
   locale_t locale,
   va_list argptr
);
```

### <a name="parameters"></a>Parametreler

*formatını*<br/>
Biçim belirtimi.

*argptr*<br/>
Bağımsız değişken listesi işaretçisi.

*locale*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için bkz. [Biçim belirtimi sözdizimi: printf ve wprintf işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

Bir çıkış hatası oluşursa, yazılan karakterlerin sayısı veya negatif bir değer.

Bu işlevlerin daha az güvenli sürümleri gibi, *Biçim* null Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Ayrıca, bu işlevlerin daha az güvenli sürümlerinden farklı olarak, *Biçim* geçerli bir biçim belirtmezse geçersiz bir parametre özel durumu oluşturulur. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler bir hata kodu döndürür ve **errno** öğesini bu hata koduna ayarlar. Varsayılan hata kodu, daha belirli bir değer uygulanmadığından, **EINVAL** .

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri bağımsız değişken listesi için bir işaretçi alır ve sonra verilen verileri biçimlendirir ve konsola yazar. **_vcwprintf_s** , **_vcprintf_s** geniş karakter sürümüdür. Bağımsız değişken olarak geniş karakterli bir dize alır.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli yerel ayar yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

> [!IMPORTANT]
> *Biçimin* Kullanıcı tanımlı bir dize olmadığından emin olun. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vtcprintf_s**|**_vcprintf_s**|**_vcprintf_s**|**_vcwprintf_s**|
|**_vtcprintf_s_l**|**_vcprintf_s_l**|**_vcprintf_s_l**|**_vcwprintf_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üstbilgiler|
|-------------|---------------------|----------------------|
|**_vcprintf_s**, **_vcprintf_s_l**|\<conio.h> ve \<stdarg.h>|\<varargs.h>*|
|**_vcwprintf_s**, **_vcwprintf_s_l**|\<conio.h> or \<wchar.h> ve \<stdarg.h>|\<varargs.h>*|

\* UNIX V uyumluluğu için gereklidir.

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

> [!IMPORTANT]
> Windows 10 sürüm 2004 (derleme 19041) ' den başlayarak, `printf` işlev ailesi, yuvarlama IÇIN ıeee 754 kurallarına göre tam olarak gösterilemeyen kayan nokta numaralarını yazdırır. Önceki Windows sürümlerinde, ' 5 ' ile biten tam olarak gösterilemeyen kayan noktalı sayılar her zaman yukarı yuvarlar. IEEE 754, en yakın çift basamağa ("Banker ' de yuvarlama" olarak da bilinir) yuvarlayabilmeleri gerektiğini belirtir. Örneğin, her ikisi `printf("%1.0f", 1.5)` de `printf("%1.0f", 2.5)` 2 ' ye yuvarlanmalıdır. 1,5, daha önce 2,5 2 ' ye yuvarlayacağından, 3 ' e yuvarlanacak. Bu değişiklik yalnızca tam olarak gösterilebilir tablo numaralarını etkiler. Örneğin, 2,35 (bellekte temsil edildiğinde, 2.35000000000000008 'e yaklaşmışsa), 2,4 ' e yuvarlamaya devam eder. Bu işlevler tarafından yapılan yuvarlama artık tarafından ayarlanan kayan nokta yuvarlama moduna da uyar [`fesetround`](fegetround-fesetround2.md) . Daha önce, yuvarlama her zaman açık `FE_TONEAREST` davranış. Bu değişiklik yalnızca Visual Studio 2019 sürüm 16,2 ve üzeri kullanılarak oluşturulan programları etkiler. Eski kayan nokta yuvarlama davranışını kullanmak için bağlantısını kullanın [`legacy_stdio_float_rounding.obj`](../link-options.md) .

## <a name="example"></a>Örnek

```cpp
// crt_vcprintf_s.cpp
#include <conio.h>
#include <stdarg.h>

// An error formatting function used to print to the console.
int eprintf_s(const char* format, ...)
{
    va_list args;
    va_start(args, format);
    int result = _vcprintf_s(format, args);
    va_end(args);
    return result;
}

int main()
{
    eprintf_s("(%d:%d): Error %s%d : %s\n", 10, 23, "C", 2111,
              "<some error text>");
    eprintf_s("    (Related to symbol '%s' defined on line %d).\n",
              "<symbol>", 5 );
}
```

```Output
(10,23): Error C2111 : <some error text>
    (Related to symbol '<symbol>' defined on line 5).
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf Işlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
[_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](cprintf-cprintf-l-cwprintf-cwprintf-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
