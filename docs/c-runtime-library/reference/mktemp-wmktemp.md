---
title: _mktemp, _wmktemp
ms.date: 11/04/2016
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
ms.openlocfilehash: c1c5f0ee12c9e07d76405014bb4a6a6ecc7d97e6
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 11/09/2018
ms.locfileid: "51326270"
---
# <a name="mktemp-wmktemp"></a>_mktemp, _wmktemp

Benzersiz bir dosya adı oluşturur. Bu işlevlerin daha güvenli sürümleri mevcuttur; bkz: [_mktemp_s, _wmktemp_s](mktemp-s-wmktemp-s.md).

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

Bu işlevlerin her biri için değiştirilmiş nameTemplate bir işaretçi döndürür. İşlev döndürür **NULL** varsa *nameTemplate* hatalı oluşturulmuş ya da daha fazla benzersiz adlar belirtilen nameTemplate oluşturulabilir.

## <a name="remarks"></a>Açıklamalar

**_Mktemp** işlevi değiştirerek benzersiz bir dosya adı oluşturur *nameTemplate* bağımsız değişken. **_mktemp** uygun şekilde çok baytlı karakter dizesi bağımsız değişkenleri çalışma zamanı sistemi tarafından çok baytlı karakter sıralarını şu anda çok baytlı kod sayfasına göre algılamayı otomatik olarak işler. **_wmktemp** geniş karakterli sürümüdür **_mktemp**; bağımsız değişkeni ve dönüş değeri **_wmktemp** geniş karakterli dizelerdir. **_wmktemp** ve **_mktemp** aynı şekilde, hariç davranır **_wmktemp** çok baytlı karakter dizelerini işlemez.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp**|**_mktemp**|**_mktemp**|**_wmktemp**|

*NameTemplate* bağımsız değişkeni olan form *temel*XXXXXX, burada *temel* sağladığınız yeni dosya adının bir parçasıdır ve her X tarafından sağlanan bir karakter için bir yer tutucudur **_mktemp**. Her bir yer tutucu karakteri *nameTemplate* bir büyük harf Mac'inizi olmalıdır **_mktemp** korur *temel* ve alfabetik bir karakter ile ilk sonunda X değiştirir. **_mktemp** aşağıdaki sondaki değiştirir X'lerin beş basamaklı değerle; bu işlem, veya birden çok iş parçacıklı programlarda, çağıran iş parçacığı arama tanımlayan benzersiz bir numara değerdir.

Her başarılı çağrı **_mktemp** değiştirir *nameTemplate*. Aynı işlem veya iş parçacığı aynı sonraki her çağrıda *nameTemplate* bağımsız değişkeni, **_mktemp** adlarıyla tarafından döndürülen dosya adlarını denetler **_mktemp** içinde Önceki çağırır. Hiçbir dosya için bir verilen ad, varsa **_mktemp** adı döndürür. Tüm adlar, daha önce döndürülen için dosyalar mevcutsa **_mktemp** kullanılan harfle sonraki kullanılabilir, 'a' ila 'z', sırası daha önce döndürülen adında alfabetik karakter değiştirerek yeni bir ad oluşturur. Örneğin, varsa *temel* olan:

> **fn**

beş basamaklı değeri tarafından sağlanan **_mktemp** 12345, döndürülen adı:

> **fna12345**

Bu ad FNA12345 dosyası oluşturmak için kullanılır ve bu dosyayı yine de, aynı işlem ya da aynı iş parçacığı sonraki adı bir çağrıda döndürülen varsa *temel* için *nameTemplate* olan:

> **fnb12345**

FNA12345 yoksa, döndürülen İleri yeniden adıdır:

> **fna12345**

**_mktemp** 26 benzersiz dosya adları, verilen herhangi bir birleşimini için en fazla oluşturabilirsiniz *temel* ve *nameTemplate* değerleri. Bu nedenle, FNZ12345 benzersiz dosya soyadıdır **_mktemp** oluşturabilirsiniz *temel* ve *nameTemplate* Bu örnekte kullanılan değerler.

Hata durumunda, **errno** ayarlanır. Varsa *nameTemplate* biçimi geçersiz (örneğin, 6'dan az X'lerin), **errno** ayarlanır **EINVAL**. Varsa **_mktemp** 26 tüm olası dosya adları zaten mevcut olduğundan, benzersiz bir ad oluşturamıyor **_mktemp** nameTemplate boş dize olarak ayarlar ve döndürür **EEXIST**.

C++'da, bu işlevler, bu işlevlerin daha yeni ve güvenli karşılıklarını çağırma şablon aşırı yüklemeleri vardır. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mktemp**|\<io.h >|
|**_wmktemp**|\<io.h > veya \<wchar.h >|

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

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile](tmpfile.md)<br/>
