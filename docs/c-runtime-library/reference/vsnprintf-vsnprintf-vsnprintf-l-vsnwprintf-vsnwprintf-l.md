---
title: vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l
description: Vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf ve _vsnwprintf_l için API başvurusu; bağımsız değişken listesi için bir işaretçi kullanarak biçimlendirilen çıktıyı yazma.
ms.date: 06/24/2020
api_name:
- _vsnprintf
- _vsnprintf_l
- _vsnwprintf
- _vsnwprintf_l
- _vsnprintf
- _vsnprintf;
- vsnprintf; _vsnprintf
- _vsnwprintf;
- _vsnprintf_l;
- _vsnwprintf_l;
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
- ntoskrnl.exe
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _vsnprintf
- _vsnwprintf
- _vsntprintf
- vsnprintf
- stdio/vsnprintf
- stdio/_vsnprintf
- stdio/_vsnprintf_l
- stdio/_vsnwprintf
- stdio/_vsnwprintf_l
- _vsnprintf_l
- _vsnwprintf_l
helpviewer_keywords:
- vsntprintf function
- _vsnwprintf_l function
- vsnwprintf_l function
- vsntprintf_l function
- _vsntprintf function
- _vsnprintf_l function
- vsnprintf function
- _vsntprintf_l function
- vsnprintf_l function
- _vsnwprintf function
- _vsnprintf function
- formatted text [C++]
- vsnwprintf function
ms.assetid: a97f92df-c2f8-4ea0-9269-76920d2d566a
ms.openlocfilehash: e6ed3d146458f514691fe0b20a4c88ffebb5f877
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008690"
---
# <a name="vsnprintf-_vsnprintf-_vsnprintf_l-_vsnwprintf-_vsnwprintf_l"></a>vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l

Bağımsız değişken listesi için bir işaretçi kullanarak biçimli çıktı yazın. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l](vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md).

## <a name="syntax"></a>Sözdizimi

```C
int vsnprintf(
   char *buffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf(
   char *buffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_l(
   char *buffer,
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vsnwprintf(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   va_list argptr
);
int _vsnwprintf_l(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
template <size_t size>
int vsnprintf(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnprintf(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnprintf_l(
   char (&buffer)[size],
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf_l(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
); // C++ only
```

### <a name="parameters"></a>Parametreler

*arabelleğin*<br/>
Çıktı için depolama konumu.

*count*<br/>
Yazılacak maksimum karakter sayısı.

*formatını*<br/>
Biçim belirtimi.

*argptr*<br/>
Bağımsız değişken listesi işaretçisi.

*locale*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için bkz. [Biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

**Vsnprintf** işlevi, sonlandıran null karakteri saymayan yazılan karakter sayısını döndürür. *Count* tarafından belirtilen arabellek boyutu, *Format* ve *argptr*tarafından belirtilen çıktıyı içermesi için yeterince büyük değilse **vsnprintf** dönüş değeri yazılacak karakter sayısıdır, *sayı* yeterince büyükse null karakteri saymaz. Dönüş değeri *sayı* -1 ' den büyükse, çıkış fazlalıkları kesilir. -1 ' in dönüş değeri bir kodlama hatası oluştuğunu gösterir.

**_Vsnprintf** ve **_vsnwprintf** işlevleri, yazılacak karakter sayısı sayıdan küçük veya buna eşit olduğunda yazılan karakter sayısını *döndürür.* Yazılacak karakter *sayısı sayı değerinden büyükse, bu*işlevler çıktının kesilmediğini belirten-1 döndürür.

Bu işlevlerin döndürdüğü değer Sonlandırıcı null, bir tane yazılıp yazılmadığını içermez.

- *Count* değeri sıfırsa ve *buffer* **null**ise, döndürülen değer işlevlerin yazacağı karakter sayısıdır. Değer, bir Sonlandırıcı **null**değeri hesaba almıyor. Bu sonucu, dize için yeterli arabellek alanı ve onun Sonlandırıcı null ayırmak için kullanabilir ve sonra, arabelleği dolduracak şekilde işlevi yeniden çağırabilir.
- *Count* değeri sıfırsa ancak *buffer* **null**değilse, hiçbir şey yazılmaz ve işlev döndürülür `-1` .
- *Biçim* **null**ise veya *arabellek* **null** ise ve *sayı* sıfıra eşit değilse, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1 döndürür ve **errno** , **EINVAL**olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri bağımsız değişken listesi için bir işaretçi alır, ardından verileri biçimlendirir ve *arabelleğe*göre işaret eden belleğe *sayı* karakteri yazar. **Vsnprintf** işlevi, çıktıyı kesen bile her zaman bir null Sonlandırıcı yazar. **_Vsnprintf** ve **_vsnwprintf**kullanılırken, arabellek yalnızca sonda yer alıyorsa (yani, yazılacak *karakter sayısı sayıdan küçükse) null*olarak sonlandırılır.

> [!IMPORTANT]
> Belirli güvenlik riskleri türlerini engellemek için, *biçimin* Kullanıcı tanımlı bir dize olmadığından emin olun. Daha fazla bilgi için bkz. [arabellek taşmalarını önleme](/windows/win32/SecBP/avoiding-buffer-overruns).

> [!NOTE]
> **_Vsnprintf**, **_vsnprintf_l**, **_vsnwprintf** ve **_vsnwprintf_l**çağrılırken, Sonlandırıcı null için yer olduğundan emin olmak için, *Count* 'un arabellek uzunluğundan kesinlikle daha az olduğundan emin olun ve işlevi çağırmadan önce arabelleği null olarak başlatın.
>
> **Vsnprintf** her zaman Sonlandırıcı null değerini yazdığından, *Count* parametresi arabelleğin boyutuna eşit olabilir.

Visual Studio 2015 ve Windows 10 ' da UıCRT ile başlayarak, **vsnprintf** artık **_vsnprintf**ile aynı değildir. **Vsnprintf** işlevi C99 standardına uyar; **_vnsprintf** , eski Visual Studio kodu ile geriye dönük uyumluluk için tutulur.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

C++ ' da, bu işlevlerin, bu işlevlerin daha yeni ve güvenli bir şekilde çağrılmasını sağlayan şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsntprintf**|**_vsnprintf**|**_vsnprintf**|**_vsnwprintf**|
|**_vsntprintf_l**|**_vsnprintf_l**|**_vsnprintf_l**|**_vsnwprintf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli üst bilgi (C)|Gerekli üst bilgi (C++)|
|-------------|---------------------------|-------------------------------|
|**vsnprintf**, **_vsnprintf** **_vsnprintf_l**|\<stdio.h>|\<stdio.h> veya \<cstdio>|
|**_vsnwprintf**, **_vsnwprintf_l**|\<stdio.h> veya \<wchar.h>|\<stdio.h>, \<wchar.h> , \<cstdio> veya \<cwchar>|

**_Vsnprintf**, **_vsnprintf_l**, **_vsnwprintf** ve **_vsnwprintf_l** işlevleri Microsoft 'a özgüdür. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example-use-wide-characters-with-_vsnwprintf"></a>Örnek: ile geniş karakterler kullanın `_vsnwprintf()`

```C
// crt_vsnwprintf.c
// compile by using: cl /W3 crt_vsnwprintf.c

// To turn off error C4996, define this symbol:
#define _CRT_SECURE_NO_WARNINGS

#include <stdio.h>
#include <wtypes.h>

#define BUFFCOUNT (10)

void FormatOutput(LPCWSTR formatstring, ...)
{
    int nSize = 0;
    wchar_t buff[BUFFCOUNT];
    memset(buff, 0, sizeof(buff));
    va_list args;
    va_start(args, formatstring);
    // Note: _vsnwprintf is deprecated; consider vsnwprintf_s instead
    nSize = _vsnwprintf(buff, BUFFCOUNT - 1, formatstring, args); // C4996
    wprintf(L"nSize: %d, buff: %ls\n", nSize, buff);
    va_end(args);
}

int main() {
    FormatOutput(L"%ls %ls", L"Hi", L"there");
    FormatOutput(L"%ls %ls", L"Hi", L"there!");
    FormatOutput(L"%ls %ls", L"Hi", L"there!!");
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: -1, buff: Hi there!
```

Bunun yerine vsnprintf kullanırsanız ve dar dize parametreleriyle birlikte davranış değişir. *Count* parametresi arabelleğin tamamının boyutu olabilir ve dönüş değeri, *sayı* yeterince büyükse yazılacak olan karakter sayısıdır:

## <a name="example-use-vsnprintf-with-narrow-strings"></a>Örnek: `vsnprintf()` dar dizeler Ile kullanın

```C
// crt_vsnprintf.c
// compile by using: cl /W4 crt_vsnprintf.c
#include <stdio.h>
#include <stdarg.h> // for va_list, va_start
#include <string.h> // for memset

#define BUFFCOUNT (10)

void FormatOutput(char* formatstring, ...)
{
    int nSize = 0;
    char buff[BUFFCOUNT];
    memset(buff, 0, sizeof(buff));
    va_list args;
    va_start(args, formatstring);
    nSize = vsnprintf(buff, sizeof(buff), formatstring, args);
    printf("nSize: %d, buff: %s\n", nSize, buff);
    va_end(args);
}

int main() {
    FormatOutput("%s %s", "Hi", "there");   //  8 chars + null
    FormatOutput("%s %s", "Hi", "there!");  //  9 chars + null
    FormatOutput("%s %s", "Hi", "there!!"); // 10 chars + null
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: 10, buff: Hi there!
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf Işlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
[Biçim belirtimi sözdizimi: printf ve wprintf Işlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \_ _swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
