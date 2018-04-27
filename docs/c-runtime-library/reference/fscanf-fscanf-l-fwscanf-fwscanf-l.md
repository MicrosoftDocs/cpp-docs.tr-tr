---
title: fscanf, _fscanf_l, fwscanf, _fwscanf_l | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- fscanf
- _fwscanf_l
- _fscanf_l
- fwscanf
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
- fscanf
- fwscanf
- _ftscanf_l
- _fwscanf_l
- _ftscanf
- _fscanf_l
dev_langs:
- C++
helpviewer_keywords:
- fscanf function
- fwscanf function
- formatted data [C++], reading from streams
- ftscanf_l function
- _ftscanf_l function
- _fwscanf_l function
- data [CRT], reading from streams
- _fscanf_l function
- ftscanf function
- fscanf_l function
- streams [C++], reading formatted data from
- _ftscanf function
- fwscanf_l function
ms.assetid: 9004e978-6c5f-4bb2-98fd-51e5948933f2
caps.latest.revision: 24
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a2334998ab246d6406dbac6d877b6e710d3dfc79
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/20/2018
---
# <a name="fscanf-fscanfl-fwscanf-fwscanfl"></a>fscanf, _fscanf_l, fwscanf, _fwscanf_l

Okuma akışı verilerden biçimlendirilmiş. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md).

## <a name="syntax"></a>Sözdizimi

```C
int fscanf(
   FILE *stream,
   const char *format [,
   argument ]...
);
int _fscanf_l(
   FILE *stream,
   const char *format,
   locale_t locale [,
   argument ]...
);
int fwscanf(
   FILE *stream,
   const wchar_t *format [,
   argument ]...
);
int _fwscanf_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale [,
   argument ]...
);
```

### <a name="parameters"></a>Parametreler

*Akış*<br/>
İşaretçi **dosya** yapısı.

*Biçimi*<br/>
Biçim denetimi dizesi.

*Bağımsız değişken*<br/>
İsteğe bağlı bağımsız değişkenler.

*Yerel ayar*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri başarıyla dönüştürülür ve atanan alan sayısını döndürür; dönüş değerini okumak ancak atanmamış alanları içermez. Dönüş değeri 0, hiçbir alan atandığını belirtir. Bir hata oluşursa veya dosya akışı sonuna ilk dönüştürmeden önce dönüş değeri **EOF** için **fscanf** ve **fwscanf**.

Bu işlevler kendi parametreleri doğrulayın. Varsa *akış* veya *biçimi* null işaretçi açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Yürütme devam etmek için izin verilip verilmediğini, bu işlevlerin dönüş **EOF** ve **errno** için **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**Fscanf** işlevi geçerli konumunu veri okuyan *akış* tarafından verilen konumları içine *bağımsız değişkeni* (varsa). Her *bağımsız değişkeni* bir tür belirteci karşılık gelen bir türde bir değişken için bir işaretçi olmalıdır *biçimi*. *Biçim* giriş yorumu alanları ve aynı denetimleri form ve olarak işlev *biçimi* bağımsız değişkeni için **scanf**; bkz [scanf](scanf-scanf-l-wscanf-wscanf-l.md) için bir Açıklama *biçimi*.

**fwscanf** bir joker karakter sürümü **fscanf**; biçim bağımsız değişkeni **fwscanf** bir joker karakter dizesidir. Akış ANSI modunda açtıysanız bu işlevler aynı aynı şekilde davranır. **fscanf** UNICODE akışı girişten şu anda desteklemiyor.

Bu işlevleri sürümlerini **_l** soneki, geçerli iş parçacığı yerel ayar yerine geçirilen yerel ayar parametresi kullanmasını dışında aynıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ftscanf**|**fscanf**|**fscanf**|**fwscanf**|
|**_ftscanf_l**|**_fscanf_l**|**_fscanf_l**|**_fwscanf_l**|

Daha fazla bilgi için bkz: [biçim belirtimi alanları - işlevler scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fscanf**, **_fscanf_l**|\<stdio.h >|
|**fwscanf**, **_fwscanf_l**|\<stdio.h > veya \<wchar.h >|

Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fscanf.c
// compile with: /W3
// This program writes formatted
// data to a file. It then uses fscanf to
// read the various data back from the file.

#include <stdio.h>

FILE *stream;

int main( void )
{
   long l;
   float fp;
   char s[81];
   char c;

   if( fopen_s( &stream, "fscanf.out", "w+" ) != 0 )
      printf( "The file fscanf.out was not opened\n" );
   else
   {
      fprintf( stream, "%s %ld %f%c", "a-string",
               65000, 3.14159, 'x' );
      // Security caution!
      // Beware loading data from a file without confirming its size,
      // as it may lead to a buffer overrun situation.

      // Set pointer to beginning of file:
      fseek( stream, 0L, SEEK_SET );

      // Read data back from file:
      fscanf( stream, "%s", s );   // C4996
      fscanf( stream, "%ld", &l ); // C4996

      fscanf( stream, "%f", &fp ); // C4996
      fscanf( stream, "%c", &c );  // C4996
      // Note: fscanf is deprecated; consider using fscanf_s instead

      // Output data read:
      printf( "%s\n", s );
      printf( "%ld\n", l );
      printf( "%f\n", fp );
      printf( "%c\n", c );

      fclose( stream );
   }
}
```

```Output
a-string
65000
3.141590
x
```

## <a name="see-also"></a>Ayrıca bkz.

[Akış g/ç](../../c-runtime-library/stream-i-o.md)<br/>
[_cscanf, _cscanf_l, _cwscanf, _cwscanf_l](cscanf-cscanf-l-cwscanf-cwscanf-l.md)<br/>
[fprintf, _fprintf_l, fwprintf, _fwprintf_l](fprintf-fprintf-l-fwprintf-fwprintf-l.md)<br/>
[scanf, _scanf_l, wscanf, _wscanf_l](scanf-scanf-l-wscanf-wscanf-l.md)<br/>
[sscanf, _sscanf_l, swscanf, _swscanf_l](sscanf-sscanf-l-swscanf-swscanf-l.md)<br/>
[fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)<br/>
