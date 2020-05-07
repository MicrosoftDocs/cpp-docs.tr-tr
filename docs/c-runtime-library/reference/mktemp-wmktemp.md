---
title: _mktemp, _wmktemp
ms.date: 4/2/2020
api_name:
- _wmktemp
- _mktemp
- _o__mktemp
- _o__wmktemp
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
- api-ms-win-crt-stdio-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _tmktemp
- wmktemp
- tmktemp
- _wmktemp
- _mktemp
helpviewer_keywords:
- _wmktemp function
- _mktemp function
- files [C++], temporary
- tmktemp function
- _tmktemp function
- wmktemp function
- mktemp function
- temporary files [C++]
ms.assetid: 055eb539-a8c2-4a7d-be54-f5b6d1eb5c85
ms.openlocfilehash: 536a63841c6e29fa003eb8b99c896f6d1cf5519f
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919097"
---
# <a name="_mktemp-_wmktemp"></a>_mktemp, _wmktemp

Benzersiz bir dosya adı oluşturur. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz. [_mktemp_s, _wmktemp_s](mktemp-s-wmktemp-s.md).

## <a name="syntax"></a>Sözdizimi

```C
char *_mktemp(
   char *nameTemplate
);
wchar_t *_wmktemp(
   wchar_t *nameTemplate
);
template <size_t size>
char *_mktemp(
   char (&nameTemplate)[size]
); // C++ only
template <size_t size>
wchar_t *_wmktemp(
   wchar_t (&nameTemplate)[size]
); // C++ only
```

### <a name="parameters"></a>Parametreler

*nameTemplate*<br/>
Dosya adı deseninin.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri değiştirilmiş nameTemplate için bir işaretçi döndürür. *Nametemplate* hatalı biçimlendirilmişse veya verilen nametemplate 'ten daha fazla benzersiz ad oluşturuoluşturulamadığı takdirde işlev **null** değerini döndürür.

## <a name="remarks"></a>Açıklamalar

**_Mktemp** Işlevi, *nametemplate* bağımsız değişkenini değiştirerek benzersiz bir dosya adı oluşturur. **_mktemp** çok baytlı karakter dizesi bağımsız değişkenlerini uygun şekilde otomatik olarak işler ve çok baytlı karakter dizilerini, çalışma zamanı sistemi tarafından kullanılmakta olan çok baytlı kod sayfasına göre tanıyor. **_wmktemp** , **_mktemp**geniş karakterli bir sürümüdür; **_wmktemp** bağımsız değişkeni ve dönüş değeri geniş karakterli dizelerdir. **_wmktemp** ve **_mktemp** aynı şekilde davranır, ancak **_wmktemp** çok baytlı karakter dizelerini işlemez.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp**|**_mktemp**|**_mktemp**|**_wmktemp**|

*Nametemplate* bağımsız değişkeninin *taban*xxxxxx vardır; burada *temel* , sağladığınız yeni dosya adının bir parçası ve her bir X **_mktemp**tarafından sağlanan bir karakter için yer tutucudur. *Nametemplate* içindeki her yer tutucu karakterin bir büyük X olması gerekir **_mktemp** . _mktemp *temeli* korur ve ilk sondaki X 'i alfabetik bir karakterle değiştirir. **_mktemp** aşağıdaki sondaki X değerlerini beş basamaklı bir değerle değiştirir; Bu değer, çağıran işlemi veya çok iş parçacıklı programları çağıran iş parçacığını tanımlayan benzersiz bir sayıdır.

Her başarılı **_mktemp** çağrısı *nametemplate*'i değiştirir. Aynı işlem veya aynı *Nametemplate* bağımsız değişkenine sahip iş parçacığından sonraki her çağrıda, **_mktemp** önceki çağrılarında **_mktemp** tarafından döndürülen adlarla eşleşen dosya adlarını denetler. Belirli bir ad için dosya yoksa **_mktemp** , bu adı döndürür. Daha önce döndürülen tüm adlara ait dosyalar varsa **_mktemp** , daha önce döndürülen adda kullanılan alfabetik karakteri, ' a '-' z ' değerinden sırasıyla bir sonraki kullanılabilir küçük harfle değiştirerek yeni bir ad oluşturur. Örneğin, *temel* :

> **FN**

**_mktemp** tarafından sağlanan beş basamaklı değer 12345, döndürülen ilk ad:

> **fna12345**

Bu ad, FNA12345 dosyası oluşturmak için kullanılırsa ve bu dosya hala mevcutsa, aynı işlemden veya *Nametemplate* için aynı *temele* sahip iş parçacığından yapılan bir çağrıda döndürülen bir sonraki ad şunlardır:

> **fnb12345**

FNA12345 yoksa, döndürülen bir sonraki ad tekrar olur:

> **fna12345**

**_mktemp** , herhangi bir *taban* ve *nametemplate* değeri bileşimi için en fazla 26 benzersiz dosya adı oluşturabilir. Bu nedenle, FNZ12345, bu örnekte kullanılan *temel* ve *nametemplate* değerleri için **_mktemp** , en son benzersiz dosya adıdır.

Hatada, **errno** ayarlanır. *Nametemplate* geçersiz bir biçime sahipse (örneğin, 6 X 'den az), **errno** **EINVAL**olarak ayarlanır. **_Mktemp** , tüm 26 olası dosya adı zaten mevcut olduğundan benzersiz bir ad oluşturamadığı için, **_mktemp** nametemplate 'i boş bir dizeye ayarlar ve **eexist**' ı döndürür.

C++ ' da, bu işlevlerin, bu işlevlerin daha yeni ve güvenli bir şekilde çağrılmasını sağlayan şablon aşırı yüklemeleri vardır. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mktemp**|\<GÇ. h>|
|**_wmktemp**|\<GÇ. h> veya \<wchar. h>|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```C
// crt_mktemp.c
// compile with: /W3
/* The program uses _mktemp to create
* unique filenames. It opens each filename
* to ensure that the next name is unique.
*/

#include <io.h>
#include <string.h>
#include <stdio.h>
#include <errno.h>

char *template = "fnXXXXXX";
char *result;
char names[27][9];

int main( void )
{
   int i;
   FILE *fp;

   for( i = 0; i < 27; i++ )
   {
      strcpy_s( names[i], sizeof( names[i] ), template );
      /* Attempt to find a unique filename: */
      result = _mktemp( names[i] );  // C4996
      // Note: _mktemp is deprecated; consider using _mktemp_s instead
      if( result == NULL )
      {
         printf( "Problem creating the template\n" );
         if (errno == EINVAL)
         {
             printf( "Bad parameter\n");
         }
         else if (errno == EEXIST)
         {
             printf( "Out of unique filenames\n");
         }
      }
      else
      {
         fopen_s( &fp, result, "w" );
         if( fp != NULL )
            printf( "Unique filename is %s\n", result );
         else
            printf( "Cannot open %s\n", result );
         fclose( fp );
      }
   }
}
```

```Output
Unique filename is fna03912
Unique filename is fnb03912
Unique filename is fnc03912
Unique filename is fnd03912
Unique filename is fne03912
Unique filename is fnf03912
Unique filename is fng03912
Unique filename is fnh03912
Unique filename is fni03912
Unique filename is fnj03912
Unique filename is fnk03912
Unique filename is fnl03912
Unique filename is fnm03912
Unique filename is fnn03912
Unique filename is fno03912
Unique filename is fnp03912
Unique filename is fnq03912
Unique filename is fnr03912
Unique filename is fns03912
Unique filename is fnt03912
Unique filename is fnu03912
Unique filename is fnv03912
Unique filename is fnw03912
Unique filename is fnx03912
Unique filename is fny03912
Unique filename is fnz03912
Problem creating the template.
Out of unique filenames.
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya IŞLEME](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile](tmpfile.md)<br/>
