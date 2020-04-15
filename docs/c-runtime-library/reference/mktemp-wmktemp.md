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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 8affd20ca7826f0d383f749567c9625d61dacd48
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338714"
---
# <a name="_mktemp-_wmktemp"></a>_mktemp, _wmktemp

Benzersiz bir dosya adı oluşturur. Bu işlevlerin daha güvenli sürümleri mevcuttur; [_mktemp_s, _wmktemp_s](mktemp-s-wmktemp-s.md)bakın.

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

Bu işlevlerin her biri değiştirilen ad Şablonu için bir işaretçi döndürür. *NameTemplate* kötü oluşturulmuşsa veya verilen adŞablon'dan daha fazla benzersiz ad oluşturulamazsa işlev **NULL** döndürür.

## <a name="remarks"></a>Açıklamalar

**_mktemp** *işlevi, nameTemplate* bağımsız değişkenini değiştirerek benzersiz bir dosya adı oluşturur. **_mktemp,** çalışma zamanı sistemi tarafından kullanılmakta olan çok bayt kod sayfasına göre çok bayt karakter dizilerini tanıyarak, çok bayt karakterli dize bağımsız değişkenlerini otomatik olarak işler. **_wmktemp** **_mktemp**geniş karakterli bir versiyonudur; _wmktemp bağımsız değişkeni **_wmktemp** ve geri dönüş değeri geniş karakterli dizeleridir. **_wmktemp** ve **_mktemp,** **_wmktemp** çok bayt karakterli dizeleri işlememesi dışında aynı şekilde davranan.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp**|**_mktemp**|**_mktemp**|**_wmktemp**|

*nameTemplate* bağımsız değişkeni, *temelin* sağladığınız yeni dosya adının bir parçası olduğu ve her X'in **_mktemp**tarafından sağlanan bir karakter için yer tutucu olduğu form *tabanı*XXXXXX'e sahiptir. *nameTemplate'deki* her yer tutucu karakter, bir büyük Harf X olmalıdır **_mktemp** *tabanı* korur ve ilk sırada yer alan X'i alfabetik bir karakterle değiştirir. **_mktemp** aşağıdaki x'leri beş basamaklı bir değerle değiştirir; bu değer, arama işlemini tanımlayan benzersiz bir sayıdır veya çok iş parçacığı olan programlarda arama iş parçacığıdır.

**_mktemp** için her başarılı çağrı *nameTemplate*değiştirir. Aynı işlemden veya aynı *ad Şablon* argümanına sahip iş parçacığından sonraki her çağrıda, önceki aramalarda **_mktemp** döndürülen adlarla eşleşen dosya adlarını **_mktemp** denetler. Belirli bir ad için dosya yoksa, **_mktemp** bu adı döndürür. Daha önce döndürülen tüm adlar için dosyalar varsa, **_mktemp,** daha önce döndürülen adda kullandığı alfabetik karakteri 'a' ile 'z' arasında sırayla bir sonraki kullanılabilir küçük harfle değiştirerek yeni bir ad oluşturur. Örneğin, *taban:*

> **Fn**

ve **_mktemp** tarafından sağlanan beş basamaklı değer 12345, döndürülen ilk ad:

> **fna12345**

Bu ad FNA12345 dosyasını oluşturmak için kullanılırsa ve bu dosya hala varsa, aynı işlemden veya *nameTemplate* için aynı *temele* sahip iş parçacığından gelen bir çağrıda döndürülen sonraki ad şudur:

> **fnb12345**

FNA12345 yoksa, döndürülen sonraki ad yeniden dir:

> **fna12345**

**_mktemp,** verilen *temel* ve *adŞablon* değerlerinin herhangi bir birleşimi için en fazla 26 benzersiz dosya adı oluşturabilir. Bu nedenle, FNZ12345, bu örnekte kullanılan *temel* ve *nameTemplate* değerleri için _mktemp **oluşturabileceğiniz** son benzersiz dosya adıdır.

Başarısızlıkta, **errno** ayarlanır. *nameTemplate* geçersiz bir biçimi varsa (örneğin, 6 X'ten az), **errno** **EINVAL**olarak ayarlanır. **_mktemp,** 26 olası dosya adının tümü zaten mevcut olduğundan benzersiz bir ad oluşturamıyorsa, **_mktemp** nameTemplate'i boş bir dizeye ayarlar ve **EEXIST**döndürür.

C++'da, bu işlevlerin daha yeni ve güvenli karşıtlarını çağıran şablon aşırı yüklemeleri vardır. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mktemp**|\<io.h>|
|**_wmktemp**|\<io.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile](tmpfile.md)<br/>
