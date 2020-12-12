---
description: 'Hakkında daha fazla bilgi edinin: fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l'
title: fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l
ms.date: 11/04/2016
api_name:
- fwscanf_s
- _fscanf_s_l
- _fwscanf_s_l
- fscanf_s
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
- _fwscanf_s_l
- _fscanf_s_l
- fscanf_s
- _ftscanf_s_l
- _ftscanf_s
- fwscanf_s
helpviewer_keywords:
- formatted data [C++], reading from streams
- _ftscanf_s_l function
- _fscanf_s_l function
- ftscanf_s function
- fwscanf_s function
- _ftscanf_s function
- data [CRT], reading from streams
- _fwscanf_s_l function
- fscanf_s function
- fwscanf_s_l function
- ftscanf_s_l function
- streams [C++], reading formatted data from
- fscanf_s_l function
ms.assetid: b6e88194-714b-4322-be82-1cc0b343fe01
ms.openlocfilehash: ae5d0c953cb46850cf56a4ce4113e5831518ae5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124923"
---
# <a name="fscanf_s-_fscanf_s_l-fwscanf_s-_fwscanf_s_l"></a>fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l

Bir akıştan biçimlendirilen verileri okur. [Fscanf, _fscanf_l, fwscanf _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md) bu SÜRÜMLERINDE, [CRT 'daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleri vardır.

## <a name="syntax"></a>Sözdizimi

```C
int fscanf_s(
   FILE *stream,
   const char *format [,
   argument ]...
);
int _fscanf_s_l(
   FILE *stream,
   const char *format,
   locale_t locale [,
   argument ]...
);
int fwscanf_s(
   FILE *stream,
   const wchar_t *format [,
   argument ]...
);
int _fwscanf_s_l(
   FILE *stream,
   const wchar_t *format,
   locale_t locale [,
   argument ]...
);
```

### <a name="parameters"></a>Parametreler

*ka*<br/>
**Dosya** yapısına yönelik işaretçi.

*formatını*<br/>
Biçim denetimi dizesi.

*değişkendir*<br/>
İsteğe bağlı bağımsız değişkenler.

*locale*<br/>
Kullanılacak yerel ayar.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri, başarıyla dönüştürülen ve atanan alanların sayısını döndürür; dönüş değeri, okunan ancak atanmamış alanları içermez. 0 dönüş değeri hiçbir alan atanmadığını gösterir. Bir hata oluşursa veya dosya akışının sonuna ilk dönüştürmeden önce ulaşılırsa, **fscanf_s** ve **fwscanf_s** için dönüş değeri **EOF** olur.

Bu işlevler, parametrelerini doğrular. *Stream* geçersiz bir dosya işaretçisiyse veya *Biçim* null işaretçisiyse, bu işlevler [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisini çağırır. Yürütmenin devam etmesine izin veriliyorsa, bu işlevler **EOF** döndürür ve **errno** , **EINVAL** olarak ayarlanır.

## <a name="remarks"></a>Açıklamalar

**Fscanf_s** işlevi, geçerli *akış* konumundaki verileri *bağımsız değişken* (varsa) tarafından verilen konumlara okur. Her *bağımsız değişken* , *biçimdeki* bir tür belirticisine karşılık gelen bir tür değişkenine bir işaretçi olmalıdır. *Biçim* , giriş alanlarının yorumunu denetler ve **scanf_s** için *Biçim* bağımsız değişkeniyle aynı forma ve işleve sahiptir; *Biçimlendirme açıklaması için bkz.* [Biçim belirtimi alanları: scanf ve wscanf işlevleri](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md) .  **fwscanf_s** , **fscanf_s** geniş karakterli bir sürümüdür; **fwscanf_s** biçim bağımsız değişkeni, geniş karakterli bir dizedir. Bu işlevler akış ANSI modunda açılırsa aynı şekilde davranır. **fscanf_s** , UNICODE akışından girişi desteklememektedir.

Daha güvenli işlevler ( **_s** sonekine sahiptir) ve diğer sürümler arasındaki temel fark, daha güvenli işlevlerin her **c**, **c**, **s**, **s** ve **[** Type alanının karakter cinsinden boyutunun, değişkenin hemen ardından gelen bir bağımsız değişken olarak geçirilmesi için gerekli olması gerektiğidir. Daha fazla bilgi için bkz. [scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md) ve [scanf genişlik belirtimi](../../c-runtime-library/scanf-width-specification.md).

> [!NOTE]
> Boyut parametresi **`unsigned`** **size_t** değil türündedir.

**_L** sonekine sahip bu işlevlerin sürümleri, geçerli iş parçacığı yerel ayarı yerine geçirilen yerel ayar parametresini kullanmaları dışında aynıdır.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmadı|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_ftscanf_s**|**fscanf_s**|**fscanf_s**|**fwscanf_s**|
|**_ftscanf_s_l**|**_fscanf_s_l**|**_fscanf_s_l**|**_fwscanf_s_l**|

## <a name="requirements"></a>Gereksinimler

|İşlev|Gerekli başlık|
|--------------|---------------------|
|**fscanf_s**, **_fscanf_s_l**|\<stdio.h>|
|**fwscanf_s**, **_fwscanf_s_l**|\<stdio.h> veya \<wchar.h>|

Ek uyumluluk bilgileri için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_fscanf_s.c
// This program writes formatted
// data to a file. It then uses fscanf to
// read the various data back from the file.

#include <stdio.h>
#include <stdlib.h>

FILE *stream;

int main( void )
{
   long l;
   float fp;
   char s[81];
   char c;

   errno_t err = fopen_s( &stream, "fscanf.out", "w+" );
   if( err )
      printf_s( "The file fscanf.out was not opened\n" );
   else
   {
      fprintf_s( stream, "%s %ld %f%c", "a-string",
               65000, 3.14159, 'x' );
      // Set pointer to beginning of file:
      fseek( stream, 0L, SEEK_SET );

      // Read data back from file:
      fscanf_s( stream, "%s", s, _countof(s) );
      fscanf_s( stream, "%ld", &l );

      fscanf_s( stream, "%f", &fp );
      fscanf_s( stream, "%c", &c, 1 );

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

[Akış G/Ç](../../c-runtime-library/stream-i-o.md)<br/>
[_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l](cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md)<br/>
[fprintf_s, _fprintf_s_l, fwprintf_s, _fwprintf_s_l](fprintf-s-fprintf-s-l-fwprintf-s-fwprintf-s-l.md)<br/>
[scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l](scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)<br/>
[sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md)<br/>
[fscanf, _fscanf_l, fwscanf, _fwscanf_l](fscanf-fscanf-l-fwscanf-fwscanf-l.md)<br/>
