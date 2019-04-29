---
title: sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l
ms.date: 11/04/2016
apiname:
- _sscanf_s_l
- sscanf_s
- _swscanf_s_l
- swscanf_s
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
- _stscanf_s
- sscanf_s
- swscanf_s
- _swscanf_s_l
- _stscanf_s_l
- _sscanf_s_l
helpviewer_keywords:
- stscanf_s_l function
- stscanf_s function
- swscanf_s function
- swscanf_s_l function
- sscanf_s_l function
- _stscanf_s_l function
- strings [C++], reading data from
- sscanf_s function
- _swscanf_s_l function
- _stscanf_s function
- reading data, strings
- strings [C++], reading
- _sscanf_s_l function
ms.assetid: 956e65c8-00a5-43e8-a2f2-0f547ac9e56c
ms.openlocfilehash: 07911b7254e74c28310669a697c7492b69567b7f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62354803"
---
# <a name="sscanfs-sscanfsl-swscanfs-swscanfsl"></a>sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l

Biçimlendirilmiş verileri bir dizeden okur. Bu sürümleri [sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md) açıklandığı gibi güvenlik geliştirmeleri vardır [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
int sscanf_s(
   const char *buffer,
   const char *format [,
   argument ] ...
);
int _sscanf_s_l(
   const char *buffer,
   const char *format,
   locale_t locale [,
   argument ] ...
);
int swscanf_s(
   const wchar_t *buffer,
   const wchar_t *format [,
   argument ] ...
);
int _swscanf_s_l(
   const wchar_t *buffer,
   const wchar_t *format,
   locale_t locale [,
   argument ] ...
);
```

### <a name="parameters"></a>Parametreler

*Arabellek*<br/>
Depolanan veri

*Biçim*<br/>
Biçim denetimi dizesi. Daha fazla bilgi için [biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler

*Yerel ayar*<br/>
Kullanılacak yerel ayar

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, başarıyla dönüştürülen ve atanan alanların sayısını döndürür; dönüş değeri, Okunmuş ancak atanmamış alanları içermez. 0 değeri hiçbir alan atanmamış belirtir. Dönüş değeri **EOF** bir hata için veya ilk dönüştürmeden önce dizenin sonuna ulaşılırsa.

Varsa *arabellek* veya *biçimi* olduğu bir **NULL** işaretçiyse, geçersiz parametre işleyicisi çağrılır, açıklandığı [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse, bu işlevler -1 döndürür ve **errno** için **EINVAL**

Bu ve diğer hata kodları hakkında daha fazla bilgi için bkz: [errno _doserrno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).

## <a name="remarks"></a>Açıklamalar

**Sscanf_s** işlevi, verileri okuyan *arabellek* her tarafından verilen konuma *bağımsız değişken*. İçinde bir tür belirleyiciye karşılık gelen bir türe sahip değişkenler işaretçileri sonra biçim dizesi bağımsız değişkenleri belirtmeniz *biçimi*. Daha az güvenli sürümünün aksine [sscanf](sscanf-sscanf-l-swscanf-swscanf-l.md), türü alan karakterleri kullandığınızda bir arabellek büyüklüğü parametresi gereklidir **c**, **C**, **s**, **S**, veya dize içine alınan denetim kümeleri **[]**. Karakter arabelleği boyutu, bunu gerektiren hemen her arabellek parametresinden sonra ek bir parametre olarak sağlanmalıdır. Örneğin, bir dizeye okuyorsanız, bu dize için arabellek boyutu şöyle aktarılır:

```C
wchar_t ws[10];
swscanf_s(in_str, L"%9s", ws, (unsigned)_countof(ws)); // buffer size is 10, width specification is 9
```

Arabellek boyutu sondaki null karakterini içerir. Bir genişlik belirtimi alanı, okunan belirtecin arabelleğe sığmasını sağlamak için kullanılabilir. Hiçbir genişlik belirtimi alanı kullanılmazsa ve okunan belirteç arabelleğe sığamayacak kadar büyük ise, hiçbir şey o arabelleğe yazılır.

Karakterler söz konusu olduğunda, tek bir karakter aşağıdaki gibi okunabilir:

```C
wchar_t wc;
swscanf_s(in_str, L"%c", &wc, 1);
```

Bu örnekte, giriş dizesi tek bir karakter okur ve ardından bir geniş karakter arabelleğinde depolar. Değersiz olmayan sonlandırılmış dizeler için birden çok karakter okurken, işaretsiz tamsayılar genişlik belirtimi ve arabellek boyutu kullanılır.

```C
char c[4];
sscanf_s(input, "%4c", &c, (unsigned)_countof(c)); // not null terminated
```

Daha fazla bilgi için [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) ve [scanf türü alan karakterleri](../../c-runtime-library/scanf-type-field-characters.md).

> [!NOTE]
> Boyut parametresi türünde **işaretsiz**değil **size_t**. 64-bit hedefler için derleme yaparken dönüştürmek için bir statik atama kullanın **_countof** veya **sizeof** doğru boyuta sonuçları.

*Biçimi* giriş alanlarının yorumunu aynı bağımsız değişkeni denetler ve form ve işleve *biçimi* için bağımsız değişken **scanf_s** işlevi. Çakışan dizeler arasında kopyalama olursa davranış tanımsızdır.

**swscanf_s** geniş karakterli sürümüdür **sscanf_s**; bağımsız değişkenler **swscanf_s** geniş karakterli dizelerdir. **sscanf_s** çok baytlı onaltılı karakter işlemez. **swscanf_s** tam genişlikli onaltılık Unicode veya "uyumluluk bölgesi" karakterlerini işlemez. Aksi takdirde, **swscanf_s** ve **sscanf_s** aynı şekilde davranır.

Sahip bu işlevlerin sürümleri **_l** sonekine dışında geçerli iş parçacığı yerel ayarı yerine iletilen yerel ayar parametresini kullanırlar.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_stscanf_s**|**sscanf_s**|**sscanf_s**|**swscanf_s**|
|**_stscanf_s_l**|**_sscanf_s_l**|**_sscanf_s_l**|**_swscanf_s_l**|

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**sscanf_s**, **_sscanf_s_l**|\<stdio.h >|
|**swscanf_s**, **_swscanf_s_l**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_sscanf_s.c
// This program uses sscanf_s to read data items
// from a string named tokenstring, then displays them.

#include <stdio.h>
#include <stdlib.h>

int main( void )
{
   char  tokenstring[] = "15 12 14...";
   char  s[81];
   char  c;
   int   i;
   float fp;

   // Input various data from tokenstring:
   // max 80 character string plus null terminator
   sscanf_s( tokenstring, "%s", s, (unsigned)_countof(s) );
   sscanf_s( tokenstring, "%c", &c, (unsigned)sizeof(char) );
   sscanf_s( tokenstring, "%d", &i );
   sscanf_s( tokenstring, "%f", &fp );

   // Output the data read
   printf_s( "String    = %s\n", s );
   printf_s( "Character = %c\n", c );
   printf_s( "Integer:  = %d\n", i );
   printf_s( "Real:     = %f\n", fp );
}
```

```Output
String    = 15
Character = 1
Integer:  = 15
Real:     = 15.000000
```

## <a name="see-also"></a>Ayrıca bkz.

[Stream g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)<br/>
[snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l](snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)<br/>
