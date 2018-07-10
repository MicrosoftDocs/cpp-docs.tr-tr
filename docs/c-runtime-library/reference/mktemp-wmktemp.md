---
title: _mktemp, _wmktemp | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- _wmktemp
- _mktemp
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
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tmktemp
- wmktemp
- tmktemp
- _wmktemp
- _mktemp
dev_langs:
- C++
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
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 087348b3cc59fb1b47699fc0e64f533c22d992b4
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/03/2018
ms.locfileid: "32404353"
---
# <a name="mktemp-wmktemp"></a>_mktemp, _wmktemp

Benzersiz bir dosya adı oluşturur. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_mktemp_s, _wmktemp_s](mktemp-s-wmktemp-s.md).

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
Dosya adı deseni.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her biri bir işaretçi değiştirilmiş nameTemplate döndürür. İşlevi döndürür **NULL** varsa *nameTemplate* hatalı biçimlendirilmiş ya da daha fazla benzersiz adlar verilen nameTemplate oluşturulabilir.

## <a name="remarks"></a>Açıklamalar

**_Mktemp** işlev değiştirerek benzersiz bir dosya adı oluşturur *nameTemplate* bağımsız değişkeni. **_mktemp** çalışma zamanı sistem tarafından şu anda kullanımda birden çok baytlı kod sayfasına göre çok baytlı karakter sıralarının algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak yönetir. **_wmktemp** bir joker karakter sürümü **_mktemp**; bağımsız değişkeni ve dönüş değeri **_wmktemp** joker karakter dizelerdir. **_wmktemp** ve **_mktemp** aynı şekilde Aksi takdirde, dışında davranır **_wmktemp** çok baytlı karakter dizeleri işlemez.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp**|**_mktemp**|**_mktemp**|**_wmktemp**|

*NameTemplate* bağımsız değişkenini içeriyor formun *temel ** XXXXXX*, burada *temel* sağladığınız yeni dosya adı parçası ve her X tarafından sağlanan bir karakter için bir yer tutucudur **_mktemp**. Her yer tutucu karakter *nameTemplate* bir büyük harf x olmalıdır **_mktemp** korur *temel* ve ilk sonunda X alfabetik bir karakter ile değiştirir. **_mktemp** aşağıdaki sondaki değiştirir X'lerin beş basamaklı değerle; bu değer sürecini veya birden çok iş parçacıklı programlar çağıran iş parçacığı arama tanımlayan benzersiz bir sayıdır.

Her başarılı çağrısı **_mktemp** değiştirir *nameTemplate*. Aynı işlem ya da aynı iş parçacığı sonraki her çağrıda *nameTemplate* bağımsız değişkeni, **_mktemp** tarafından döndürülen adlarıyla dosya adları için denetimleri **_mktemp** içinde Önceki çağırır. Bir verilen ad için hiçbir dosya varsa, **_mktemp** bu adını döndürür. Tüm adlar, döndürülen için dosyalar varsa **_mktemp** kullanılan sonraki kullanılabilir küçük harf, sırayla 'a' ile 'z' ile daha önce döndürülen adı alfasayısal bir karakter değiştirerek yeni bir ad oluşturur. Örneğin, varsa *temel* değil:

> **fn**

tarafından sağlanan beş basamaklı değeri **_mktemp** 12345, ilk döndürülen adıdır:

> **fna12345**

Bu ad FNA12345 dosyası oluşturmak için kullanılır ve bu dosyayı yine, sonraki adı aynı işlem ya da aynı iş parçacığı bir çağrıda döndürülen varsa *temel* için *nameTemplate* değil:

> **fnb12345**

FNA12345 mevcut değilse döndürülen sonraki yeniden adıdır:

> **fna12345**

**_mktemp** en fazla 26 benzersiz dosya adları için belirtilen herhangi bir bileşimini oluşturabilirsiniz *temel* ve *nameTemplate* değerleri. Bu nedenle, FNZ12345 son benzersiz dosya adıdır **_mktemp** için oluşturabilirsiniz *temel* ve *nameTemplate* Bu örnekte kullanılan değerler.

Hata durumunda, **errno** ayarlanır. Varsa *nameTemplate* biçimi geçersiz (örneğin, 6 daha az X'lerin), **errno** ayarlanır **EINVAL**. Varsa **_mktemp** tüm 26 olası dosya adları zaten var olduğundan, benzersiz bir ad oluşturamıyor **_mktemp** nameTemplate boş bir dize olarak ayarlar ve döndürür **EEXIST**.

C++'da, bu işlevlerin daha yeni, güvenli ortaklarınıza çağırma şablon aşırı yüklemeleri bu işlevler vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mktemp**|\<io.h >|
|**_wmktemp**|\<io.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).

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

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile](tmpfile.md)<br/>
