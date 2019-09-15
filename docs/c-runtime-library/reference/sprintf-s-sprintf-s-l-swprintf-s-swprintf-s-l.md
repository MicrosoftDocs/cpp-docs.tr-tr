---
title: sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l
ms.date: 11/04/2016
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
ms.assetid: 424f0a29-22ef-40e8-b565-969f5f57782f
ms.openlocfilehash: 34b3ddce68563479b26abff34e8fa31f6298558a
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70958017"
---
# <a name="sprintf_s-_sprintf_s_l-swprintf_s-_swprintf_s_l"></a>sprintf_s, _sprintf_s_l, swprintf_s, _swprintf_s_l

Biçimlendirilen verileri bir dizeye yazın. Bunlar, [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi [sprintf, _sprintf_l, \_swprintf, _swprintf_l ve _swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) güvenlik geliştirmeleriyle ilgili sürümleridir.

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

*format*<br/>
Biçim denetimi dizesi

*...*<br/>
Biçimlendirilecek isteğe bağlı bağımsız değişkenler

*ayarlar*<br/>
Kullanılacak yerel ayar.

Daha fazla bilgi için bkz. [Biçim belirtimleri](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).

## <a name="return-value"></a>Dönüş Değeri

Bir hata oluştuysa yazılan karakter sayısı veya-1. *Arabellek* veya *Biçim* null işaretçisiyse, **sprintf_s** ve **swprintf_s** Return-1 ' i döndürür ve **errno** öğesini **EINVAL**olarak ayarlayın.

**sprintf_s** , Sonlandırıcı null karakteri saymayan *arabellekte*depolanan bayt sayısını döndürür. **swprintf_s** , sondaki null geniş karakteri saymayan *arabellekte*depolanan geniş karakter sayısını döndürür.

## <a name="remarks"></a>Açıklamalar

**Sprintf_s** işlevi, *arabellekteki*bir dizi karakter ve değeri biçimlendirir ve depolar. Her *bağımsız değişken* (varsa), karşılık *gelen biçim belirtimine*göre dönüştürülür ve çıktı. Biçim sıradan karakterlerden oluşur ve [printf](printf-printf-l-wprintf-wprintf-l.md)için *Biçim* bağımsız değişkeniyle aynı form ve işleve sahiptir. Yazılan son karakterden sonra null bir karakter eklenir. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

**Sprintf_s** ve [sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) arasındaki bir temel fark, **sprintf_s** 'in geçerli biçimlendirme karakterleri için biçim dizesini denetlemesini, ancak [sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) yalnızca biçim dizesinin veya arabelleğin **null** işaretçiler olup olmadığını denetler. Her iki denetim de başarısız olursa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa işlev-1 döndürür ve **errno** öğesini **EINVAL**olarak ayarlar.

**Sprintf_s** ve [sprintf](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md) arasındaki diğer temel fark, **sprintf_s** 'nin karakter cinsinden çıkış arabelleğinin boyutunu belirten bir length parametresi alacağından emin olur. Arabellek, Sonlandırıcı null dahil olmak üzere biçimlendirilen metin için çok küçük ise, *arabellek [0*] olarak null bir karakter yerleştirerek ve geçersiz parametre işleyicisi çağrıldığında arabellek boş bir dizeye ayarlanır. **_Snprintf**'den farklı olarak, **sprintf_s** arabellek boyutu sıfır olmadığı takdirde arabelleğin null olarak sonlandırılacağını garanti eder.

**swprintf_s** , **sprintf_s**öğesinin geniş karakterli bir sürümüdür; **swprintf_s** işaretçi bağımsız değişkenleri geniş karakterli dizelerdir. **Swprintf_s** ' deki kodlama hatalarının algılanması **sprintf_s**içindeki öğesinden farklı olabilir. **_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

' C++De, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir, bu da bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

Arabellek çok küçük olduğunda ne olacağı hakkında ek denetim sunan **sprintf_s** sürümleri vardır. Daha fazla bilgi için bkz. [_snprintf_s, _snprintf_s_l, _snwprintf_s, _snwprintf_s_l](snprintf-s-snprintf-s-l-snwprintf-s-snwprintf-s-l.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNıCODE & _MBCS tanımlı değil|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stprintf_s**|**sprintf_s**|**sprintf_s**|**swprintf_s**|
|**_stprintf_s_l**|**_sprintf_s_l**|**_sprintf_s_l**|**_swprintf_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**sprintf_s**, **_sprintf_s_l**|C: \<stdio. h ><br /><br /> C++: \<cstdio > veya \<stdio. h >|
|**swprintf_s**, **_swprintf_s_l**|C: \<stdio. h > veya \<wchar. h ><br /><br /> C++: \<cstdio >, \<cwchar >, \<stdio. h > veya \<wchar. h >|

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

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[printf, _printf_l, wprintf, _wprintf_l](printf-printf-l-wprintf-wprintf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, __swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[vprintf İşlevleri](../../c-runtime-library/vprintf-functions.md)<br/>
