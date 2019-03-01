---
title: vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l
ms.date: 11/04/2016
apiname:
- _vsnwprintf_s
- _vsnwprintf_s_l
- _vsnprintf_s
- vsnprintf_s
- _vsnprintf_s_l
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
- ntdll.dll
- ucrtbase.dll
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- _vsnprintf_s
- _vsntprintf_s
- _vsnwprintf_s
helpviewer_keywords:
- vsnwprintf_s function
- _vsntprintf_s function
- _vsntprintf_s_l function
- vsntprintf_s function
- vsnwprintf_s_l function
- vsnprintf_s_l function
- vsntprintf_s_l function
- _vsnwprintf_s_l function
- _vsnprintf_s function
- vsnprintf_s function
- _vsnprintf_s_l function
- _vsnwprintf_s function
- formatted text [C++]
ms.assetid: 147ccfce-58c7-4681-a726-ef54ac1c604e
ms.openlocfilehash: 255c3b760dec1495a4f9a82915878a5504844f24
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210711"
---
# <a name="vsnprintfs-vsnprintfs-vsnprintfsl-vsnwprintfs-vsnwprintfsl"></a>vsnprintf_s, _vsnprintf_s, _vsnprintf_s_l, _vsnwprintf_s, _vsnwprintf_s_l

Bağımsız değişkenler listesine bir işaretçi kullanarak biçimlendirilmiş çıktı yazın. Bunlar sürümleridir [vsnprintf, _vsnprintf, _vsnprintf_l, _vsnwprintf, _vsnwprintf_l](vsnprintf-vsnprintf-vsnprintf-l-vsnwprintf-vsnwprintf-l.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
int vsnprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   va_list argptr
);
int _vsnprintf_s_l(
   char *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const char *format,
   locale_t locale,
   va_list argptr
);
int _vsnwprintf_s(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const wchar_t *format,
   va_list argptr
);
int _vsnwprintf_s_l(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   size_t count,
   const wchar_t *format,
   locale_t locale,
   va_list argptr
);
template <size_t size>
int _vsnprintf_s(
   char (&buffer)[size],
   size_t count,
   const char *format,
   va_list argptr
); // C++ only
template <size_t size>
int _vsnwprintf_s(
   wchar_t (&buffer)[size],
   size_t count,
   const wchar_t *format,
   va_list argptr
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Çıktı için depolama konumu.

*sizeOfBuffer*<br/>
Boyutu *arabellek* çıkışını karakter sayısı için.

*Sayısı*<br/>
En fazla (Sonlandırıcı null içermeden), yazılacak karakter sayısı veya [_TRUNCATE](../../c-runtime-library/truncate.md).

*Biçim*<br/>
Biçim belirtimi.

*argptr*<br/>
Bağımsız değişkenler listesine işaretçi.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için [biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

**vsnprintf_s**, **_vsnprintf_s** ve **_vsnwprintf_s** bir hata oluşursa, sonlandırıcı null veya negatif bir değer içermeyen yazılan karakter sayısını döndürür. **vsnprintf_s** aynıdır **_vsnprintf_s**. **vsnprintf_s** ANSI standardı için uyumluluk için dahildir. **_vnsprintf** geriye dönük uyumluluk için tutulmaktadır.

Veri ve sonlandırıcı bir null depolamak için gereken depolama alanı aşarsa *sizeOfBuffer*, açıklanan şekilde geçersiz parametre işleyicisi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md)sürece *sayısı*  olduğu [_TRUNCATE](../../c-runtime-library/truncate.md), bu durumda çok dize olarak sığacak *arabellek* yazılır ve -1 döndürdü. Geçersiz parametre işleyicisi sonra yürütülmesine devam ederse, bu işlevler kümesi *arabellek* boş bir dize olarak ayarlanmış **errno** için **ERANGE**ve -1 döndürür.

Varsa *arabellek* veya *biçimi* olduğu bir **NULL** işaretçisi veya *sayısı* küçük veya ona eşit sıfır olarak geçersiz parametre işleyicisi çağrılır. Yürütme devam etmesine izin verilirse bu işlevler kümesi **errno** için **EINVAL** ve -1 döndürür.

### <a name="error-conditions"></a>Hata koşulları

|**Koşul**|döndürülecek|**errno**|
|-----------------|------------|-------------|
|*Arabellek* olduğu **NULL**|-1|**EINVAL**|
|*Biçim* olduğu **NULL**|-1|**EINVAL**|
|*sayısı* < = 0|-1|**EINVAL**|
|*sizeOfBuffer* çok küçük (ve *sayısı* ! = **_TRUNCATE**)|-1 (ve *arabellek* boş bir dize olarak ayarlanmış)|**ERANGE**|

## <a name="remarks"></a>Açıklamalar

Bu işlevlerin her biri bir bağımsız değişken listesi için bir işaretçi alır sonra biçimlendirir ve en fazla Yazar *sayısı* bellek belirtilen verileri karakteri tarafından işaret edilen *arabellek* ve sonlandırıcı bir null ekler.

Varsa *sayısı* olduğu [_TRUNCATE](../../c-runtime-library/truncate.md), bu işlevler daha uygun şekilde dize olarak yazın ardından *arabellek* bir sonlandırıcı null yer bırakmak çalışırken. Tüm dize (Sonlandırıcı null ile) sığacak *arabellek*, ardından bu işlevler (Sonlandırıcı null içermeden) yazılan karakter sayısını döndürür; Aksi takdirde, bu işlevler, kesme belirtmek için -1 döndürür oluştu.

Sahip bu işlevlerin sürümleri **_l** sonekine, geçerli iş parçacığı yerel ayarı yerine iletilen yerel ayar parametresini kullanmalarıdır.

> [!IMPORTANT]
> Emin *biçimi* kullanıcı tanımlı bir dize değil. Daha fazla bilgi için [arabellek taşmalarını](/windows/desktop/SecBP/avoiding-buffer-overruns).

> [!NOTE]
> Sonlandırıcı null yer olduğundan emin olmak için olduğundan emin olun *sayısı* arabellek uzunluğu veya kullanım kesinlikle küçük olan **_TRUNCATE**.

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kalkar) ve bunlar otomatik olarak eski ve güvenli olmayan işlevlerle daha yeni ve güvenli karşılıklarını değiştirir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_vsntprintf_s**|**_vsnprintf_s**|**_vsnprintf_s**|**_vsnwprintf_s**|
|**_vsntprintf_s_l**|**_vsnprintf_s_l**|**_vsnprintf_s_l**|**_vsnwprintf_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|İsteğe bağlı üst bilgiler|
|-------------|---------------------|----------------------|
|**vsnprintf_s**|\<stdio.h > ve \<stdarg.h >|\<XENIX > *|
|**_vsnprintf_s**, **_vsnprintf_s_l**|\<stdio.h > ve \<stdarg.h >|\<XENIX > *|
|**_vsnwprintf_s**, **_vsnwprintf_s_l**|\<stdio.h > veya \<wchar.h >, ve \<stdarg.h >|\<XENIX > *|

\* UNIX V uyumluluğu için gerekli.

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```cpp
// crt_vsnprintf_s.cpp
#include <stdio.h>
#include <wtypes.h>

void FormatOutput(LPCSTR formatstring, ...)
{
   int nSize = 0;
   char buff[10];
   memset(buff, 0, sizeof(buff));
   va_list args;
   va_start(args, formatstring);
   nSize = vsnprintf_s( buff, _countof(buff), _TRUNCATE, formatstring, args);
   printf("nSize: %d, buff: %s\n", nSize, buff);
   va_end(args);
}

int main() {
   FormatOutput("%s %s", "Hi", "there");
   FormatOutput("%s %s", "Hi", "there!");
   FormatOutput("%s %s", "Hi", "there!!");
}
```

```Output
nSize: 8, buff: Hi there
nSize: 9, buff: Hi there!
nSize: -1, buff: Hi there!
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[va_arg, va_copy, va_end, va_start](va-arg-va-copy-va-end-va-start.md)<br/>
