---
title: sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l
ms.date: 11/04/2016
apiname:
- _swprintf_s_l
- _sprintf_s_l
- swprintf_s
- sprintf_s
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
- ntoskrnl.exe
apitype: DLLExport
f1_keywords:
- swprintf_s
- sprintf_s
- stdio/sprintf_s
- stdio/swprintf_s
- stdio/_sprintf_s_l
- stdio/_swprintf_s_l
- _sprintf_s_l
- _swprintf_s_l
helpviewer_keywords:
- stprintf_s function
- stprintf_s_l function
- swprintf_s_l function
- sprintf_s function
- swprintf_s function
- _swprintf_s_l function
- sprintf_s_l function
- _stprintf_s_l function
- _stprintf_s function
- _sprintf_s_l function
- formatted text [C++]
ms.assetid: 424f0a29-22ef-40e8-b565-969f5f57782f
ms.openlocfilehash: 4d4bec339caccf9b0843afada4b56b435243dd11
ms.sourcegitcommit: e06648107065f3dea35f40c1ae5999391087b80b
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/01/2019
ms.locfileid: "57210893"
---
# <a name="sprintfs-sprintfsl-swprintfs-swprintfsl"></a>sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l

Biçimlendirilmiş verileri bir dizeye yaz. Bunlar sürümleridir [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
int sprintf_s(
   char *buffer,
   size_t sizeOfBuffer,
   const char *format,
   ...
);
int _sprintf_s_l(
   char *buffer,
   size_t sizeOfBuffer,
   const char *format,
   locale_t locale,
   ...
);
int swprintf_s(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   const wchar_t *format,
   ...
);
int _swprintf_s_l(
   wchar_t *buffer,
   size_t sizeOfBuffer,
   const wchar_t *format,
   locale_t locale,
   ...
);
template <size_t size>
int sprintf_s(
   char (&buffer)[size],
   const char *format,
   ...
); // C++ only
template <size_t size>
int swprintf_s(
   wchar_t (&buffer)[size],
   const wchar_t *format,
   ...
); // C++ only
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Çıktı için depolama konumu

*sizeOfBuffer*<br/>
Depolanacak maksimum karakter sayısı.

*Biçim*<br/>
Biçim Denetimi dizesi

*...*<br/>
Biçimlendirilecek isteğe bağlı bağımsız değişkenler

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için [biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

Yazılan karakter sayısını veya bir hata oluştu, -1. Varsa *arabellek* veya *biçimi* null bir işaretçiyse, **sprintf_s** ve **swprintf_s** -1 döndürür ve **errno**için **EINVAL**.

**sprintf_s** içinde depolanan bayt sayısını döndüren *arabellek*, sondaki null karakter sayılmaz. **swprintf_s** içinde depolanan geniş karakterlerin sayısını döndürür *arabellek*, sonlandırıcı geniş null karakter sayılmaz.

## <a name="remarks"></a>Açıklamalar

**Sprintf_s** işlevi biçimlendirir ve bir dizi karakter ve değerlerini depolar *arabellek*. Her *bağımsız değişken* (varsa) dönüştürülür ve karşılık gelen kapsamındaki biçim belirtimine göre çıkışı *biçimi*. Biçim sıradan karakterlerden oluşur ve aynı forma ve işleve sahiptir *biçimi* için bağımsız değişken [printf](printf-printf-l-wprintf-wprintf-l.md). Bir null karakter son karakter yazıldıktan sonra eklenir. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

Arasında ana farklardan biri **sprintf_s** ve [sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) olan **sprintf_s** geçerli biçimlendirme karakterleri için biçim dizesi ise denetler [ sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) yalnızca biçim dize veya arabellek olup olmadığını denetler. **NULL** işaretçileri. Ya da denetim de başarısız olursa, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Devam etmek için işlev -1 döndürür ve kümeleri yürütülmesine izin veriliyorsa **errno** için **EINVAL**.

Arasındaki diğer ana fark **sprintf_s** ve [sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) olan **sprintf_s** çıktı arabelleğinin boyutunu karakter sayısı olarak belirten bir uzunluk parametresi almasıdır. Arabellek Sonlandırıcı null dahil olmak üzere biçimlendirilmiş metin için çok küçük ardından arabellek null karakter: yerleştirerek boş dize olarak ayarlanmış *arabellek*[0] ve geçersiz parametre işleyicisi çağrılır. Farklı **_snprintf**, **sprintf_s** arabellek null-arabellek boyutu sıfır değilse sonlandırılmasını garantiler.

**swprintf_s** geniş karakterli sürümüdür **sprintf_s**; işaretçi bağımsız değişkenler **swprintf_s** geniş karakterli dizelerdir. İçinde kodlama hatalarının algılanması **swprintf_s** farklı **sprintf_s**. Sahip bu işlevlerin sürümleri **_l** sonekine, geçerli iş parçacığı yerel ayarı yerine iletilen yerel ayar parametresini kullanmalarıdır.

C++'da, bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak, bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kaldırarak çıkarabilir ve bunlar otomatik olarak eski ve güvenli olmayan işlevlerle daha yeni ve güvenli karşılıklarını değiştirir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Sürümleri **sprintf_s** arabellek çok küçük olduğunda ne olacağı üzerinde ek denetim sunar. Daha fazla bilgi için [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stprintf_s**|**sprintf_s**|**sprintf_s**|**swprintf_s**|
|**_stprintf_s_l**|**_sprintf_s_l**|**_sprintf_s_l**|**_swprintf_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**sprintf_s**, **_sprintf_s_l**|C: \<stdio.h ><br /><br /> C++: \<cstdio > veya \<stdio.h >|
|**swprintf_s**, **_swprintf_s_l**|C: \<stdio.h > veya \<wchar.h ><br /><br /> C++: \<cstdio >, \<cwchar >, \<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_sprintf_s.c
// This program uses sprintf_s to format various
// data and place them in the string named buffer.
//

#include <stdio.h>

int main( void )
{
   char  buffer[200], s[] = "computer", c = 'l';
   int   i = 35, j;
   float fp = 1.7320534f;

   // Format and print various data:
   j  = sprintf_s( buffer, 200,     "   String:    %s\n", s );
   j += sprintf_s( buffer + j, 200 - j, "   Character: %c\n", c );
   j += sprintf_s( buffer + j, 200 - j, "   Integer:   %d\n", i );
   j += sprintf_s( buffer + j, 200 - j, "   Real:      %f\n", fp );

   printf_s( "Output:\n%s\ncharacter count = %d\n", buffer, j );
}
```

```Output
Output:
   String:    computer
   Character: l
   Integer:   35
   Real:      1.732053

character count = 79
```

## <a name="example"></a>Örnek

```C
// crt_swprintf_s.c
// wide character example
// also demonstrates swprintf_s returning error code
#include <stdio.h>

int main( void )
{
   wchar_t buf[100];
   int len = swprintf_s( buf, 100, L"%s", L"Hello world" );
   printf( "wrote %d characters\n", len );
   len = swprintf_s( buf, 100, L"%s", L"Hello\xffff world" );
   // swprintf_s fails because string contains WEOF (\xffff)
   printf( "wrote %d characters\n", len );
}
```

```Output
wrote 11 characters
wrote -1 characters
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
