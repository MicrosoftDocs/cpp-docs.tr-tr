---
title: _mktemp_s, _wmktemp_s
ms.date: 4/2/2020
api_name:
- _mktemp_s
- _wmktemp_s
- _o__mktemp_s
- _o__wmktemp_s
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
ms.openlocfilehash: 7834049fe8d28f7294976ac29a3daa663a06cff6
ms.sourcegitcommit: 5a069c7360f75b7c1cf9d4550446ec2fa2eb2293
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82919135"
---
# <a name="_mktemp_s-_wmktemp_s"></a>_mktemp_s, _wmktemp_s

Benzersiz bir dosya adı oluşturur. Bunlar, [CRT 'Daki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md)bölümünde açıklandığı gibi güvenlik geliştirmeleriyle [_wmktemp _mktemp](mktemp-wmktemp.md) sürümleridir.

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
Dosya adı deseninin.

*Sizeınchars*<br/>
**_Mktemp_s**; tek baytlık karakterlerle arabelleğin boyutu; null Sonlandırıcı dahil olmak üzere **_wmktemp_s**geniş karakterler.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her ikisi de başarı durumunda sıfır döndürür; hatada hata kodu.

### <a name="error-conditions"></a>Hata koşulları

|*nameTemplate*|*Sizeınchars*|Döndürülen değer|*Nametemplate* içindeki yeni değer|
|----------------|-------------------|----------------------|-------------------------------|
|**DEĞER**|kaydedilmemiş|**EıNVAL**|**DEĞER**|
|Yanlış biçim (doğru biçim için açıklamalar bölümüne bakın)|kaydedilmemiş|**EıNVAL**|boş dize|
|kaydedilmemiş|<= X 'in sayısı|**EıNVAL**|boş dize|

Yukarıdaki hata koşullarından herhangi biri oluşursa, [parametre doğrulama](../../c-runtime-library/parameter-validation.md)bölümünde açıklandığı gibi geçersiz parametre işleyicisi çağrılır. Yürütmenin devam etmesine izin veriliyorsa, **errno** **EINVAL** olarak ayarlanır ve işlevler **EINVAL**döndürür.

## <a name="remarks"></a>Açıklamalar

**_Mktemp_s** Işlevi, *nametemplate* bağımsız değişkenini değiştirerek benzersiz bir dosya adı oluşturur, böylece çağrıdan sonra *nametemplate* işaretçisi yeni dosya adını içeren bir dizeye işaret eder. **_mktemp_s** çok baytlı karakter dizesi bağımsız değişkenlerini uygun şekilde otomatik olarak işler ve çok baytlı karakter dizilerini, çalışma zamanı sistemi tarafından kullanılmakta olan çok baytlı kod sayfasına göre tanıyor. **_wmktemp_s** , **_mktemp_s**geniş karakterli bir sürümüdür; **_wmktemp_s** bağımsız değişkeni, geniş karakterli bir dizedir. **_wmktemp_s** ve **_mktemp_s** aynı şekilde davranır, ancak **_wmktemp_s** çok baytlı karakter dizelerini işlemez.

Bu işlevlerin hata ayıklama Kitaplığı sürümleri ilk olarak arabelleği 0xFE ile doldurur. Bu davranışı devre dışı bırakmak için [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamanın kapsamına alınır. Bunu değiştirmek için bkz. [CRT Içindeki genel durum](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp_s**|**_mktemp_s**|**_mktemp_s**|**_wmktemp_s**|

*Nametemplate* bağımsız değişkeninin **basexxxxxx**biçiminde olması, burada *Base* 'in sağladığınız yeni dosya adının parçası olduğu ve her bir X **_mktemp_s**tarafından sağlanan bir karakter için yer tutucudur. *Nametemplate* içindeki her yer tutucu karakterin bir büyük X olması gerekir **_mktemp_s** . _mktemp_s *temeli* korur ve ilk sondaki X 'i alfabetik bir karakterle değiştirir. **_mktemp_s** aşağıdaki sondaki X değerlerini beş basamaklı bir değerle değiştirir; Bu değer, çağıran işlemi veya çok iş parçacıklı programları çağıran iş parçacığını tanımlayan benzersiz bir sayıdır.

Her başarılı **_mktemp_s** çağrısı *nametemplate*'i değiştirir. Aynı işlem veya aynı *Nametemplate* bağımsız değişkenine sahip iş parçacığından sonraki her çağrıda, **_mktemp_s** önceki çağrılarında **_mktemp_s** tarafından döndürülen adlarla eşleşen dosya adlarını denetler. Belirli bir ad için dosya yoksa **_mktemp_s** , bu adı döndürür. Daha önce döndürülen tüm adlara ait dosyalar varsa **_mktemp_s** , daha önce döndürülen adda kullanılan alfabetik karakteri, ' a '-' z ' değerinden sırasıyla bir sonraki kullanılabilir küçük harfle değiştirerek yeni bir ad oluşturur. Örneğin, *temel* :

> **FN**

**_mktemp_s** tarafından sağlanan beş basamaklı değer 12345, döndürülen ilk ad:

> **fna12345**

Bu ad, FNA12345 dosyası oluşturmak için kullanılırsa ve bu dosya hala mevcutsa, aynı işlemden veya *Nametemplate* için aynı *temele* sahip iş parçacığından yapılan bir çağrıda döndürülen bir sonraki ad şunlardır:

> **fnb12345**

FNA12345 yoksa, döndürülen bir sonraki ad tekrar olur:

> **fna12345**

**_mktemp_s** , herhangi bir *taban* ve *nametemplate* değeri bileşimi için en fazla 26 benzersiz dosya adı oluşturabilir. Bu nedenle, FNZ12345, bu örnekte kullanılan *temel* ve *nametemplate* değerleri için **_mktemp_s** , en son benzersiz dosya adıdır.

C++ ' da, bu işlevlerin kullanılması şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkarabilir (bir boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırır) ve eski, güvenli olmayan işlevleri otomatik olarak yeni, güvenli karşılıklarıyla değiştirebilir. Daha fazla bilgi için bkz. [Güvenli şablon aşırı yüklemeleri](../../c-runtime-library/secure-template-overloads.md).

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mktemp_s**|\<GÇ. h>|
|**_wmktemp_s**|\<GÇ. h> veya \<wchar. h>|

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

[Dosya IŞLEME](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
