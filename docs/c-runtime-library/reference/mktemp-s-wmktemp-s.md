---
title: _mktemp_s, _wmktemp_s
ms.date: 11/04/2016
apiname:
- _mktemp_s
- _wmktemp_s
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
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
helpviewer_keywords:
- _tmktemp_s function
- mktemp_s function
- _wmktemp_s function
- _mktemp_s function
- files [C++], temporary
- tmktemp_s function
- wmktemp_s function
- temporary files [C++]
ms.assetid: 92a7e269-7f3d-4c71-bad6-14bc827a451d
ms.openlocfilehash: fef10f2cfbcc0332741d560a41a782b70ed14798
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/31/2018
ms.locfileid: "50590950"
---
# <a name="mktemps-wmktemps"></a>_mktemp_s, _wmktemp_s

Benzersiz bir dosya adı oluşturur. Bunlar sürümleridir [_mktemp, _wmktemp](mktemp-wmktemp.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Sözdizimi

```C
errno_t _mktemp_s(
   char *nameTemplate,
   size_t sizeInChars
);
errno_t _wmktemp_s(
   wchar_t *nameTemplate,
   size_t sizeInChars
);
template <size_t size>
errno_t _mktemp_s(
   char (&nameTemplate)[size]
); // C++ only
template <size_t size>
errno_t _wmktemp_s(
   wchar_t (&nameTemplate)[size]
); // C++ only
```

### <a name="parameters"></a>Parametreler

*nameTemplate*<br/>
Dosya adı deseni.

*sizeInChars*<br/>
Tek baytlı karakter arabellek boyutunu **_mktemp_s**; geniş öğesindeki karakterler **_wmktemp_s**, null sonlandırıcıyı da dahil olmak üzere.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her ikisi de, başarılıysa sıfır değerini döndürür; bir hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|*nameTemplate*|*sizeInChars*|Dönüş değeri|Yeni değer *nameTemplate*|
|----------------|-------------------|----------------------|-------------------------------|
|**NULL**|Tüm|**EINVAL**|**NULL**|
|Hatalı biçim (açıklamalara bakın bölümü doğru biçim için)|Tüm|**EINVAL**|Boş dize|
|Tüm|< = sayısı X'lerin|**EINVAL**|Boş dize|

Yukarıdaki hata durumlardan biri oluşursa, geçersiz parametre işleyicisi açıklandığı gibi çağrılır [Parameter Validation](../../c-runtime-library/parameter-validation.md). Yürütmenin devam etmesine izin verilirse **errno** ayarlanır **EINVAL** ve işlevleri döndürür **EINVAL**.

## <a name="remarks"></a>Açıklamalar

**_Mktemp_s** işlevi değiştirerek benzersiz bir dosya adı oluşturur *nameTemplate* bağımsız değişkeni, böylece çağrısının sonrasına *nameTemplate* işaretçisi işaret eden bir dizeye Yeni dosya adını içeren. **_mktemp_s** uygun şekilde çok baytlı karakter dizesi bağımsız değişkenleri çalışma zamanı sistemi tarafından çok baytlı karakter sıralarını şu anda çok baytlı kod sayfasına göre algılamayı otomatik olarak işler. **_wmktemp_s** geniş karakterli sürümüdür **_mktemp_s**; bağımsız değişkeni **_wmktemp_s** geniş karakterli bir dizedir. **_wmktemp_s** ve **_mktemp_s** aynı şekilde, hariç davranır **_wmktemp_s** çok baytlı karakter dizelerini işlemez.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp_s**|**_mktemp_s**|**_mktemp_s**|**_wmktemp_s**|

*NameTemplate* bağımsız değişkeni olan form **baseXXXXXX**burada *temel* sağladığınız yeni dosya adının bir parçasıdır ve her X tarafından sağlanan bir karakter için bir yer tutucudur **_mktemp_s**. Her bir yer tutucu karakteri *nameTemplate* bir büyük harf Mac'inizi olmalıdır **_mktemp_s** korur *temel* ve alfabetik bir karakter ile ilk sonunda X değiştirir. **_mktemp_s** aşağıdaki sondaki değiştirir X'lerin beş basamaklı değerle; bu işlem, veya birden çok iş parçacıklı programlarda, çağıran iş parçacığı arama tanımlayan benzersiz bir numara değerdir.

Her başarılı çağrı **_mktemp_s** değiştirir *nameTemplate*. Aynı işlem veya iş parçacığı aynı sonraki her çağrıda *nameTemplate* bağımsız değişkeni, **_mktemp_s** adlarıyla tarafından döndürülen dosya adlarını denetler **_mktemp_s** Önceki çağrılarında. Hiçbir dosya için bir verilen ad, varsa **_mktemp_s** adı döndürür. Tüm adlar, daha önce döndürülen için dosyalar mevcutsa **_mktemp_s** kullanılan harfle sonraki kullanılabilir, 'a' ila 'z', sırası daha önce döndürülen adında alfabetik karakter değiştirerek yeni bir ad oluşturur. Örneğin, varsa *temel* olan:

> **fn**

beş basamaklı değeri tarafından sağlanan **_mktemp_s** 12345, döndürülen adı:

> **fna12345**

Bu ad FNA12345 dosyası oluşturmak için kullanılır ve bu dosyayı yine de, aynı işlem ya da aynı iş parçacığı sonraki adı bir çağrıda döndürülen varsa *temel* için *nameTemplate* olan:

> **fnb12345**

FNA12345 yoksa, döndürülen İleri yeniden adıdır:

> **fna12345**

**_mktemp_s** 26 benzersiz dosya adları, verilen herhangi bir birleşimini için en fazla oluşturabilirsiniz *temel* ve *nameTemplate* değerleri. Bu nedenle, FNZ12345 benzersiz dosya soyadıdır **_mktemp_s** oluşturabilirsiniz *temel* ve *nameTemplate* Bu örnekte kullanılan değerler.

C++ dilinde bu işlevlerin kullanılması şablon aşırı yüklemeleriyle basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimi ortadan kalkar) ve bunlar otomatik olarak eski ve güvenli olmayan işlevlerle daha yeni ve güvenli karşılıklarını değiştirir. Daha fazla bilgi için [güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mktemp_s**|\<io.h >|
|**_wmktemp_s**|\<io.h > veya \<wchar.h >|

Daha fazla uyumluluk bilgisi için bkz. [Uyumluluk](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Örnek

```cpp
// crt_mktemp_s.cpp
/* The program uses _mktemp to create
* five unique filenames. It opens each filename
* to ensure that the next name is unique.
*/

#include <io.h>
#include <string.h>
#include <stdio.h>

char *fnTemplate = "fnXXXXXX";
char names[5][9];

int main()
{
   int i, err, sizeInChars;
   FILE *fp;

   for( i = 0; i < 5; i++ )
   {
      strcpy_s( names[i], sizeof(names[i]), fnTemplate );
      /* Get the size of the string and add one for the null terminator.*/
      sizeInChars = strnlen(names[i], 9) + 1;
      /* Attempt to find a unique filename: */
      err = _mktemp_s( names[i], sizeInChars );
      if( err != 0 )
         printf( "Problem creating the template" );
      else
      {
         if( fopen_s( &fp, names[i], "w" ) == 0 )
            printf( "Unique filename is %s\n", names[i] );
         else
            printf( "Cannot open %s\n", names[i] );
         fclose( fp );
      }
   }

   return 0;
}
```

### <a name="sample-output"></a>Örnek Çıktı

```Output
Unique filename is fna03188
Unique filename is fnb03188
Unique filename is fnc03188
Unique filename is fnd03188
Unique filename is fne03188
```

## <a name="see-also"></a>Ayrıca bkz.

[Dosya İşleme](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
