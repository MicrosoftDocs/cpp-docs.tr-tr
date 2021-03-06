---
description: 'Daha fazla bilgi edinin: sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l'
title: sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l
ms.date: 3/9/2021
api_name:
- __swprintf_l
- sprintf
- _sprintf_l
- _swprintf_l
- swprintf
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
- ntdll.dll
- ucrtbase.dll
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _stprintf_l
- __swprintf_l
- sprintf_l
- swprintf
- _sprintf_l
- sprintf
- _stprintf
- stprintf_l
helpviewer_keywords:
- _swprintf_l function
- _stprintf function
- __swprintf_l function
- stprintf function
- sprintf function
- _sprintf_l function
- _stprintf_l function
- swprintf function
- strings [C++], writing to
- _CRT_NON_CONFORMING_SWPRINTFS
- swprintf_l function
- stprintf_l function
- sprintf_l function
- formatted text [C++]
ms.openlocfilehash: e8a83a8c92ab873c250e94e9e9317a18c36673a2
ms.sourcegitcommit: b04b39940b0c1e265f80fc1951278fdb05a1b30a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102622107"
---
# <a name="sprintf-_sprintf_l-swprintf-_swprintf_l-__swprintf_l"></a>sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l

Biçimlendirilen verileri bir dizeye yazın. Bu işlevlerin bazılarının daha güvenli sürümleri mevcuttur; bkz. [sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l](sprintf-s-sprintf-s-l-swprintf-s-swprintf-s-l.md). **Swprintf** ve **_swprintf_l** güvenli sürümleri, arabelleğin boyutunu bir parametre olarak alır.

## <a name="syntax"></a>Sözdizimi

```C
int sprintf(
   char *buffer,
   const char *format [,
   argument] ...
);
int _sprintf_l(
   char *buffer,
   const char *format,
   locale_t locale [,
   argument] ...
);
int swprintf(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format [,
   argument]...
);
int _swprintf_l(
   wchar_t *buffer,
   size_t count,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
int __swprintf_l(
   wchar_t *buffer,
   const wchar_t *format,
   locale_t locale [,
   argument] ...
);
template <size_t size>
int sprintf(
   char (&buffer)[size],
   const char *format [,
   argument] ...
); // C++ only
template <size_t size>
int _sprintf_l(
   char (&buffer)[size],
   const char *format,
   locale_t locale [,
   argument] ...
); // C++ only
```

### <a name="parameters"></a>Parametreler

*arabelleğin*<br/>
Çıktı için depolama konumu

*biriktirme*<br/>
Bu işlevin Unicode sürümünde depolanacak en fazla karakter sayısı.

*formatını*<br/>
Biçim denetimi dizesi

*değişkendir*<br/>
İsteğe bağlı bağımsız değişkenler

*locale*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için bkz. [Biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

Bir hata oluştuysa yazılan karakter sayısı veya-1. *Arabellek* veya *Biçim* null Işaretçisiyse, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler-1 döndürür ve **errno** , **EINVAL** olarak ayarlanır.

**sprintf** , Sonlandırıcı null karakteri saymayan *arabellekte* depolanan bayt sayısını döndürür. **swprintf** , Sonlandırıcı boş geniş karakteri saymayan *arabellekte* depolanan geniş karakter sayısını döndürür.

## <a name="remarks"></a>Açıklamalar

**Sprintf** işlevi, *arabellekteki* bir dizi karakter ve değeri biçimlendirir ve depolar. Her *bağımsız değişken* (varsa), karşılık *gelen biçim belirtimine* göre dönüştürülür ve çıktı. Biçim sıradan karakterlerden oluşur ve [printf](printf-printf-l-wprintf-wprintf-l.md)için *Biçim* bağımsız değişkeniyle aynı form ve işleve sahiptir. Yazılan son karakterden sonra null bir karakter eklenir. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

> [!IMPORTANT]
> **Sprintf** kullanarak,, **sprintf** kullanan kodun arabellek taşmalarına açık olduğu anlamına gelen, yazılan karakter sayısını sınırlandırmaya yönelik bir yol yoktur. *Arabelleğe* yazılacak en fazla karakter sayısını belirten [_snprintf](snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)ilgili işlevi kullanmayı düşünün veya ne kadar büyük bir arabelleğin gerekli olduğunu anlamak için [_scprintf](scprintf-scprintf-l-scwprintf-scwprintf-l.md) kullanın. Ayrıca, *biçimin* Kullanıcı tanımlı bir dize olmadığından emin olun.
>
> Windows 10 sürüm 2004 (derleme 19041) ' den başlayarak, `printf` işlev ailesi, yuvarlama IÇIN ıeee 754 kurallarına göre tam olarak gösterilemeyen kayan nokta numaralarını yazdırır. Önceki Windows sürümlerinde, ' 5 ' ile biten tam olarak gösterilemeyen kayan noktalı sayılar her zaman yukarı yuvarlar. IEEE 754, en yakın çift basamağa ("Banker ' de yuvarlama" olarak da bilinir) yuvarlayabilmeleri gerektiğini belirtir. Örneğin, her ikisi `printf("%1.0f", 1.5)` de `printf("%1.0f", 2.5)` 2 ' ye yuvarlanmalıdır. 1,5, daha önce 2,5 2 ' ye yuvarlayacağından, 3 ' e yuvarlanacak. Bu değişiklik yalnızca tam olarak gösterilebilir tablo numaralarını etkiler. Örneğin, 2,35 (bellekte temsil edildiğinde, 2.35000000000000008 'e yaklaşmışsa), 2,4 ' e yuvarlamaya devam eder. Bu işlevler tarafından yapılan yuvarlama artık tarafından ayarlanan kayan nokta yuvarlama moduna da uyar [`fesetround`](fegetround-fesetround2.md) . Daha önce, yuvarlama her zaman açık `FE_TONEAREST` davranış. Bu değişiklik yalnızca Visual Studio 2019 sürüm 16,2 ve üzeri kullanılarak oluşturulan programları etkiler. Eski kayan nokta yuvarlama davranışını kullanmak için [' legacy_stdio_float_rounding. obj '](../link-options.md)ile bağlantı yapın.

**swprintf** , **sprintf** öğesinin geniş karakterli bir sürümüdür; **swprintf** için işaretçi bağımsız değişkenleri geniş karakterli dizelerdir. **Swprintf** içindeki kodlama hatalarının algılanması **sprintf** öğesinden farklı olabilir. **swprintf** ve **fwprintf** , **swprintf** hariç davranır. **Dosya** türünde bir hedef yerine bir dizeye çıkış yazar ve **swprintf** *Count* parametresinin yazılacak maksimum karakter sayısını belirtmesini gerektirir. **_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

**swprintf** , **size_t** türünde ikinci parametreyi ( *Count*) gerektiren ISO C standardına uyar. Olmayan eski davranışı zorlamak için **_CRT_NON_CONFORMING_SWPRINTFS** tanımlayın. Gelecekteki bir sürümde eski davranış kaldırılabilir, bu nedenle kodun yeni uyumlu davranışı kullanacak şekilde değiştirilmesi gerekir.

C++ ' da, bu işlevlerin, bu işlevlerin daha yeni ve güvenli bir şekilde çağrılmasını sağlayan şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stprintf**|**sprintf**|**sprintf**|**_swprintf**|
|**_stprintf_l**|**_sprintf_l**|**_sprintf_l**|**__swprintf_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**sprintf**, **_sprintf_l**|\<stdio.h>|
|**swprintf**, **_swprintf_l**|\<stdio.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example-use-sprintf-to-format-data"></a>Örnek: verileri biçimlendirmek için sprintf kullanın

```C
// crt_sprintf.c
// compile with: /W3
// This program uses sprintf to format various
// data and place them in the string named buffer.

#include <stdio.h>

int main( void )
{
   char  buffer[200], s[] = "computer", c = 'l';
   int   i = 35, j;
   float fp = 1.7320534f;

   // Format and print various data:
   j  = sprintf( buffer,     "   String:    %s\n", s ); // C4996
   j += sprintf( buffer + j, "   Character: %c\n", c ); // C4996
   j += sprintf( buffer + j, "   Integer:   %d\n", i ); // C4996
   j += sprintf( buffer + j, "   Real:      %f\n", fp );// C4996
   // Note: sprintf is deprecated; consider using sprintf_s instead

   printf( "Output:\n%s\ncharacter count = %d\n", buffer, j );
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

## <a name="example-error-code-handling"></a>Örnek: hata kodu işleme

```C
// crt_swprintf.c
// wide character example
// also demonstrates swprintf returning error code
#include <stdio.h>

int main( void )
{
   wchar_t buf[100];
   int len = swprintf( buf, 100, L"%s", L"Hello world" );
   printf( "wrote %d characters\n", len );
   len = swprintf( buf, 100, L"%s", L"Hello\xffff world" );
   // swprintf fails because string contains WEOF (\xffff)
   printf( "wrote %d characters\n", len );
}
```

```Output
wrote 11 characters
wrote -1 characters
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vprintf Işlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
