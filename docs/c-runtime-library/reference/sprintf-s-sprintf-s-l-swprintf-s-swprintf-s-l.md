---
description: 'Hakkında daha fazla bilgi edinin: sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l'
title: sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l
ms.date: 3/9/2021
api_name:
- _swprintf_s_l
- _sprintf_s_l
- swprintf_s
- sprintf_s
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
- ntoskrnl.exe
api_type:
- DLLExport
topic_type:
- apiref
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
ms.openlocfilehash: 323ac9531a60aaff859c18d0f0b6a3811f4ad59a
ms.sourcegitcommit: b04b39940b0c1e265f80fc1951278fdb05a1b30a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102622120"
---
# <a name="sprintf_s-_sprintf_s_l-swprintf_s-_swprintf_s_l"></a>sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l

Biçimlendirilen verileri bir dizeye yazın. Bunlar [sprintf, _sprintf_l, swprintf, _swprintf_l \_ _SWPRINTF_L,](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) [CRT 'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle sürümleridir.

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

*arabelleğin*<br/>
Çıktı için depolama konumu

*sizeOfBuffer*<br/>
Depolanacak maksimum karakter sayısı.

*formatını*<br/>
Biçim denetimi dizesi

*...*<br/>
Biçimlendirilecek isteğe bağlı bağımsız değişkenler

*locale*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için bkz. [Biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

Bir hata oluştuysa yazılan karakter sayısı veya-1. *Arabellek* veya *Biçim* null işaretçisiyse, **sprintf_s** ve **swprintf_s** -1 döndürür ve **errno** öğesini **EINVAL** olarak ayarlayın.

**sprintf_s** , sondaki null karakteri saymayan *arabellekte* depolanan bayt sayısını döndürür. **swprintf_s** , sondaki null geniş karakteri saymayan *arabellekte* depolanan geniş karakter sayısını döndürür.

## <a name="remarks"></a>Açıklamalar

**Sprintf_s** işlevi, *arabelleğe* bir dizi karakter ve değer depolar. Her *bağımsız değişken* (varsa), karşılık *gelen biçim belirtimine* göre dönüştürülür ve çıktı. Biçim sıradan karakterlerden oluşur ve [printf](printf-printf-l-wprintf-wprintf-l.md)için *Biçim* bağımsız değişkeniyle aynı form ve işleve sahiptir. Yazılan son karakterden sonra null bir karakter eklenir. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

**Sprintf_s** ve [sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) arasındaki bir temel fark, **sprintf_s** geçerli biçimlendirme karakterlerinin biçim dizesini denetlemelebilirken [sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) yalnızca biçim dizesinin veya arabelleğin **null** işaretçiler olup olmadığını denetler. Her iki denetim de başarısız olursa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa işlev-1 döndürür ve **errno** öğesini **EINVAL** olarak ayarlar.

**Sprintf_s** ve [sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) arasındaki diğer temel fark, **sprintf_s** , çıkış arabelleğinin karakter cinsinden boyutunu belirten bir length parametresi alır. Arabellek, Sonlandırıcı null dahil olmak üzere biçimlendirilen metin için çok küçük ise, *arabellek [0*] olarak null bir karakter yerleştirerek ve geçersiz parametre işleyicisi çağrıldığında arabellek boş bir dizeye ayarlanır. **_Snprintf** aksine, **sprintf_s** arabellek boyutu sıfır olmadığı takdirde arabelleğin null olarak sonlandırılacağını garanti eder.

**swprintf_s** , **sprintf_s** geniş karakterli bir sürümüdür; **swprintf_s** işaretçi bağımsız değişkenleri geniş karakterli dizelerdir. **Swprintf_s** kodlama hatalarının algılanması **sprintf_s** farklı olabilir. **_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

C++ ' da, bu işlevlerin kullanımı şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir, bu da bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Arabellek çok küçük olduğunda ne olacağı hakkında ek denetim sunan **sprintf_s** sürümleri vardır. Daha fazla bilgi için bkz. [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md).

> [!IMPORTANT]
> Windows 10 sürüm 2004 (derleme 19041) ' den başlayarak, `printf` işlev ailesi, yuvarlama IÇIN ıeee 754 kurallarına göre tam olarak gösterilemeyen kayan nokta numaralarını yazdırır. Önceki Windows sürümlerinde, ' 5 ' ile biten tam olarak gösterilemeyen kayan noktalı sayılar her zaman yukarı yuvarlar. IEEE 754, en yakın çift basamağa ("Banker ' de yuvarlama" olarak da bilinir) yuvarlayabilmeleri gerektiğini belirtir. Örneğin, her ikisi `printf("%1.0f", 1.5)` de `printf("%1.0f", 2.5)` 2 ' ye yuvarlanmalıdır. 1,5, daha önce 2,5 2 ' ye yuvarlayacağından, 3 ' e yuvarlanacak. Bu değişiklik yalnızca tam olarak gösterilebilir tablo numaralarını etkiler. Örneğin, 2,35 (bellekte temsil edildiğinde, 2.35000000000000008 'e yaklaşmışsa), 2,4 ' e yuvarlamaya devam eder. Bu işlevler tarafından yapılan yuvarlama artık tarafından ayarlanan kayan nokta yuvarlama moduna da uyar [`fesetround`](fegetround-fesetround2.md) . Daha önce, yuvarlama her zaman açık `FE_TONEAREST` davranış. Bu değişiklik yalnızca Visual Studio 2019 sürüm 16,2 ve üzeri kullanılarak oluşturulan programları etkiler. Eski kayan nokta yuvarlama davranışını kullanmak için [' legacy_stdio_float_rounding. obj '](../link-options.md)ile bağlantı yapın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stprintf_s**|**sprintf_s**|**sprintf_s**|**swprintf_s**|
|**_stprintf_s_l**|**_sprintf_s_l**|**_sprintf_s_l**|**_swprintf_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**sprintf_s**, **_sprintf_s_l**|, \<stdio.h><br /><br /> C++: \<cstdio> veya \<stdio.h>|
|**swprintf_s**, **_swprintf_s_l**|C: \<stdio.h> veya \<wchar.h><br /><br /> C++: \<cstdio> , \<cwchar> \<stdio.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example-use-sprintf_s-to-format-data"></a>Örnek: verileri biçimlendirmek için sprintf_s kullanın

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

## <a name="example-error-code-handling"></a>Örnek: hata kodu işleme

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

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vprintf Işlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
