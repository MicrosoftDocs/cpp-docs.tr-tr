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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 061c5647b2c5a5e79b017cf93989f62ad19cfc0a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338763"
---
# <a name="_mktemp_s-_wmktemp_s"></a>_mktemp_s, _wmktemp_s

Benzersiz bir dosya adı oluşturur. Bunlar, [CRT'deki](mktemp-wmktemp.md) Güvenlik Özellikleri'nde açıklandığı gibi güvenlik geliştirmeleriyle _wmktemp _mktemp [sürümleridir.](../../c-runtime-library/security-features-in-the-crt.md)

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
**_mktemp_s**tek bayt karakterlerdeki arabelleğe boyutu; **null**terminator dahil _wmktemp_s geniş karakterler.

## <a name="return-value"></a>Dönüş Değeri

Bu işlevlerin her ikisi de başarı sıfır döndürün; hata bir hata kodu.

### <a name="error-conditions"></a>Hata Koşulları

|*nameTemplate*|*sizeInChars*|Döndürülen değer|*nameTemplate'de* yeni değer|
|----------------|-------------------|----------------------|-------------------------------|
|**Null**|herhangi bir|**Eınval**|**Null**|
|Yanlış biçim (doğru biçim için Açıklamalar bölümüne bakın)|herhangi bir|**Eınval**|boş dize|
|herhangi bir|<= X'lerin sayısı|**Eınval**|boş dize|

Yukarıdaki hata koşullarından herhangi biri oluşursa, geçersiz parametre işleyicisi, [Parametre Doğrulama'da](../../c-runtime-library/parameter-validation.md)açıklandığı gibi çağrılır. Yürütme devam etmesine izin verilirse, **errno** **EINVAL** olarak ayarlanır ve işlevleri **EINVAL**döndürür.

## <a name="remarks"></a>Açıklamalar

**_mktemp_s** *işlevi, nameTemplate* bağımsız değişkenini değiştirerek benzersiz bir dosya adı oluşturur, böylece aramadan sonra *nameTemplate* işaretçisi yeni dosya adını içeren bir dizeyi gösterir. **_mktemp_s,** çoklu karakter dizelerini uygun şekilde işleyerek, çalışma zamanı sistemi tarafından kullanılmakta olan çok bayt kod sayfasına göre çok bayt karakter dizilerini tanıyarak çalışır. **_wmktemp_s** **_mktemp_s**geniş karakterli bir versiyonudur; **_wmktemp_s** bağımsız değişkeni geniş karakterli bir dizedir. **_wmktemp_s** ve **_mktemp_s,** **_wmktemp_s** çok bayt karakterli dizeleri işlememesi dışında aynı şekilde davranan.

Bu işlevlerin hata ayıklama kitaplığı sürümleri önce arabelleği 0xFE ile doldurur. Bu davranışı devre dışı kullanabilirsiniz, [_CrtSetDebugFillThreshold](crtsetdebugfillthreshold.md)kullanın.

Varsayılan olarak, bu işlevin genel durumu uygulamaya kapsamlıdır. Bunu değiştirmek için [CRT'deki Genel duruma](../global-state.md)bakın.

### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri

|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tmktemp_s**|**_mktemp_s**|**_mktemp_s**|**_wmktemp_s**|

*nameTemplate* bağımsız değişkeni **baseXXXXXX**formuna sahiptir, *burada temel,* sağladığınız yeni dosya adının bir parçasıdır ve her **X, _mktemp_s**tarafından sağlanan bir karakter için bir yer tutucudur. *nameTemplate'deki* her yer tutucu karakter, *temeli* korur **_mktemp_s** bir üst harf x olmalıdır ve ilk takip eden X'i alfabetik bir karakterle değiştirir. **_mktemp_s** aşağıdaki x'leri beş basamaklı bir değerle değiştirir; bu değer, arama işlemini tanımlayan benzersiz bir sayıdır veya çok iş parçacığı olan programlarda arama iş parçacığıdır.

**_mktemp_s** için her başarılı çağrı *nameTemplate*değiştirir. Aynı işlemden veya aynı *ad Şablon* argümanına sahip iş parçacığından sonraki her çağrıda, önceki aramalarda **_mktemp_s** döndürülen adlarla eşleşen dosya adlarını **_mktemp_s** denetler. Belirli bir ad için dosya yoksa, **_mktemp_s** bu adı döndürür. Daha önce döndürülen tüm adlar için dosyalar varsa, **_mktemp_s,** daha önce döndürülen adda kullandığı alfabetik karakteri 'a' ile 'z' arasında sırayla bir sonraki kullanılabilir küçük harfle değiştirerek yeni bir ad oluşturur. Örneğin, *taban:*

> **Fn**

ve **_mktemp_s** tarafından sağlanan beş basamaklı değer 12345, döndürülen ilk ad:

> **fna12345**

Bu ad FNA12345 dosyasını oluşturmak için kullanılırsa ve bu dosya hala varsa, aynı işlemden veya *nameTemplate* için aynı *temele* sahip iş parçacığından gelen bir çağrıda döndürülen sonraki ad şudur:

> **fnb12345**

FNA12345 yoksa, döndürülen sonraki ad yeniden dir:

> **fna12345**

**_mktemp_s,** verilen *temel* ve *adŞablon* değerlerinin herhangi bir birleşimi için en fazla 26 benzersiz dosya adı oluşturabilir. Bu nedenle, FNZ12345, bu örnekte kullanılan *taban* ve *nameTemplate* değerleri için _mktemp_s **oluşturabileceğiniz** son benzersiz dosya adıdır.

C++'da, bu işlevleri kullanmak şablon aşırı yükleri ile basitleştirilir; aşırı yüklemeler arabellek uzunluğunu otomatik olarak çıkartabilir (boyut bağımsız değişkeni belirtme gereksinimini ortadan kaldırabilir) ve eski, güvenli olmayan işlevleri yeni, güvenli karşılıklarıyla otomatik olarak değiştirebilirler. Daha fazla bilgi için Bkz. [Güvenli Şablon Overloads.](../../c-runtime-library/secure-template-overloads.md)

## <a name="requirements"></a>Gereksinimler

|Yordam|Gerekli başlık|
|-------------|---------------------|
|**_mktemp_s**|\<io.h>|
|**_wmktemp_s**|\<io.h> \<veya wchar.h>|

Daha fazla uyumluluk bilgisi için Bkz. [Uyumluluk.](../../c-runtime-library/compatibility.md)

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

[Dosya Işleme](../../c-runtime-library/file-handling.md)<br/>
[fopen, _wfopen](fopen-wfopen.md)<br/>
[_getmbcp](getmbcp.md)<br/>
[_getpid](getpid.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
[_setmbcp](setmbcp.md)<br/>
[_tempnam, _wtempnam, tmpnam, _wtmpnam](tempnam-wtempnam-tmpnam-wtmpnam.md)<br/>
[tmpfile_s](tmpfile-s.md)<br/>
