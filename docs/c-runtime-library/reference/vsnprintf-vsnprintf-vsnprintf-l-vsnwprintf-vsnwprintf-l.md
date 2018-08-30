---
title: vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
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
- ntoskrnl.exe
- ucrtbase.dll
apitype: DLLExport
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
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e5166ef52f88e714d1168fe25a1ec29dd5360205
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 08/29/2018
ms.locfileid: "43210511"
---
# <a name="vsnprintf-vsnprintf-vsnprintfl-vsnwprintf-vsnwprintfl"></a>vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l

Bağımsız değişkenler listesine bir işaretçi kullanarak biçimlendirilmiş çıktı yazın. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l](vsnprintf-s-vsnprintf-s-vsnprintf-s-l-vsnwprintf-s-vsnwprintf-s-l.md).

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

*Arabellek*<br/>
Çıktı için depolama konumu.

*Sayısı*<br/>
Yazılacak karakter sayısı.

*Biçim*<br/>
Biçim belirtimi.

*argptr*<br/>
Bağımsız değişkenler listesine işaretçi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için [biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

**Vsnprintf** işlevi, sonlandırıcı null karakter sayılmaz yazılan karakter sayısını döndürür. Belirtilen arabellek boyutu *sayısı* tarafından belirtilen çıkış içerecek şekilde yeterli büyüklükte değil *biçimi* ve *argptr*, dönüş değeri  **vsnprintf** değilse null karakter sayılmaz yazılacak karakter sayısı *sayısı* yeterince büyük olan. Dönüş değeri büyükse *sayısı* - 1, çıktı kesildi. Bir kodlama hatası oluştu-1 değeri belirtir.

Her ikisi de **_vsnprintf** ve **_vsnwprintf** işlevler yazılacak karakter sayısı veya buna eşit olup olmadığını yazılan karakter sayısını döndürür *sayısı*; numara yazılacak karakter büyükse *sayısı*, bu işlevler çıktı kesildi gösteren dönüş -1.

Bir yazıldığı veya bu işlevleri tarafından döndürülen değer, sonlandırıcı null içermez. Zaman *sayısı* sıfırsa, değeri olan işlevler yazdığınız, olmayan karakter sayısı dahil olmak üzere herhangi bir sonlandırıcı null döndürdü. Dize ve kendi Sonlandırıcı null için yeterli arabellek alanı ayırmak için bu sonucu kullanın ve ardından tekrar arabellek doldurmak için bir işlevi çağırabilir.

Varsa *biçimi* olduğu **NULL**, veya *arabellek* olduğu **NULL** ve *sayısı* sıfır olarak, bu işlevler eşit değil içinde açıklanan şekilde geçersiz parametre işleyicisi çağırır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler -1 döndürür ve **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri bir bağımsız değişken listesi için bir işaretçi alır sonra verileri biçimlendirir ve en fazla Yazar *sayısı* bellek karakter tarafından işaret edilen *arabellek*. **Vsnprintf** işlevi bile çıkış kesen bir null Sonlandırıcı her zaman yazar. Kullanırken **_vsnprintf** ve **_vsnwprintf**, arabellek null-sonunda yer yoksa sonlandırılması (diğer bir deyişle, yazılacak karakter sayısını ise küçüktür *sayısı*).

> [!IMPORTANT]
> Belirli türde bir güvenlik risklerini önlemek için emin olun *biçimi* kullanıcı tanımlı bir dize değil. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

> [!NOTE]
> Çağrılırken Sonlandırıcı null yer olmasını sağlamak üzere **_vsnprintf**, **_vsnprintf_l**, **_vsnwprintf** ve **_vsnwprintf_l**, olduğundan emin olun *sayısı* arabellek uzunluğundan kesinlikle küçük ve null işlevi çağırmadan önce arabelleğe başlatır.
>
> Çünkü **vsnprintf** her zaman Sonlandırıcı null Yazar *sayısı* parametresi arabellek boyutuna eşit olabilir.

Visual Studio 2015 ve Windows 10 UCRT itibaren **vsnprintf** artık aynıdır **_vsnprintf**. **Vsnprintf** işlevi; C99 standardı ile uyumludur **_vnsprintf** eski Visual Studio code ile geriye dönük uyumluluk için tutulmaktadır.

Sahip bu işlevlerin sürümleri **_l** sonekine, geçerli iş parçacığı yerel ayarı yerine iletilen yerel ayar parametresini kullanmalarıdır.

C++'da, bu işlevler, bu işlevlerin daha yeni ve güvenli karşılıklarını çağırma şablon aşırı yüklemeleri vardır. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsntprintf**|**_vsnprintf**|**_vsnprintf**|**_vsnwprintf**|
|**_vsntprintf_l**|**_vsnprintf_l**|**_vsnprintf_l**|**_vsnwprintf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık (C)|Gerekli başlık (C++)|
|-------------|---------------------------|-------------------------------|
|**vsnprintf**, **_vsnprintf**, **_vsnprintf_l**|\<stdio.h >|\<stdio.h > veya \<cstdio >|
|**_vsnwprintf**, **_vsnwprintf_l**|\<stdio.h > veya \<wchar.h >|\<stdio.h >, \<wchar.h >, \<cstdio >, veya \<cwchar >|

**_Vsnprintf**, **_vsnprintf_l**, **_vsnwprintf** ve **_vsnwprintf_l** Microsoft'a özgü işlevlerdir. Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

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

Vsnprintf dar dize parametreleri yanı sıra bunun yerine, kullanırsanız davranışını değiştirir. *Sayısı* parametresi, arabelleğin tamamını boyutu olabilir ve dönüş değeri, yazılmış karakter sayısı olan *sayısı* yeterince büyük:

## <a name="example"></a>Örnek

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

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
[Biçim Belirtim Sözdizimi: printf ve wprintf İşlevleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
