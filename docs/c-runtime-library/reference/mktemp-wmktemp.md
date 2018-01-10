---
title: _mktemp, _wmktemp | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
dev_langs: C++
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
caps.latest.revision: "25"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ac2fd19254cce03b7cd7efc4324f5dc03c608b7a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mktemp-wmktemp"></a>_mktemp, _wmktemp
Benzersiz bir dosya adı oluşturur. Bu işlevlerin daha güvenli sürümleri kullanılabilir; bkz: [_mktemp_s, _wmktemp_s](../../c-runtime-library/reference/mktemp-s-wmktemp-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_mktemp(  
   char *template   
);  
wchar_t *_wmktemp(  
   wchar_t *template   
);  
template <size_t size>  
char *_mktemp(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_wmktemp(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 `template`  
 Dosya adı deseni.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her biri bir işaretçi değiştirilmiş şablonu döndürür. İşlevi döndürür `NULL` varsa `template` hatalı biçimlendirilmiş ya da daha fazla benzersiz adlar verilen şablonu oluşturulabilir.  
  
## <a name="remarks"></a>Açıklamalar  
 `_mktemp` İşlev değiştirerek benzersiz bir dosya adı oluşturur `template` bağımsız değişkeni. `_mktemp`çok baytlı karakter sıralarının şu anda kullanımda birden çok baytlı kod sayfasına göre çalışma zamanı sistem tarafından algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak yönetir. `_wmktemp`bir joker karakter sürümü `_mktemp`; bağımsız değişkeni ve dönüş değeri `_wmktemp` joker karakter dizelerdir. `_wmktemp`ve `_mktemp` aynı şekilde Aksi takdirde, dışında davranır `_wmktemp` çok baytlı karakter dizeleri işlemez.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmktemp`|`_mktemp`|`_mktemp`|`_wmktemp`|  
  
 `template` Bağımsız değişkenini içeriyor formun `base` *XXXXXX*, burada `base` sağladığınız yeni dosya adı parçası ve her X tarafından sağlanan bir karakter için bir yer tutucudur `_mktemp`. Her yer tutucu karakter `template` bir büyük harf x olmalıdır `_mktemp` korur `base` ve ilk sonunda X alfabetik bir karakter ile değiştirir. `_mktemp`Aşağıdaki sondaki değiştirir X'lerin beş basamaklı değerle; Bu değer, işlem, veya birden çok iş parçacıklı programlar çağıran iş parçacığı arama tanımlayan benzersiz bir sayıdır.  
  
 Her başarılı çağrısı `_mktemp` değiştirir `template`. Aynı işlem ya da aynı iş parçacığı sonraki her çağrıda `template` bağımsız değişkeni, `_mktemp` tarafından döndürülen adlarıyla dosya adları için denetimleri `_mktemp` önceki çağrılarında. Bir verilen ad için hiçbir dosya varsa, `_mktemp` o adını döndürür. Tüm adlar, döndürülen için dosyalar varsa `_mktemp` kullanılan sonraki kullanılabilir küçük harf, sırayla 'a' ile 'z' ile daha önce döndürülen adı alfasayısal bir karakter değiştirerek yeni bir ad oluşturur. Örneğin, varsa `base` değil:  
  
```  
fn  
```  
  
 tarafından sağlanan beş basamaklı değeri `_mktemp` 12345, ilk döndürülen adıdır:  
  
```  
fna12345  
```  
  
 Bu ad FNA12345 dosyası oluşturmak için kullanılır ve bu dosyayı yine, sonraki adı aynı işlem ya da aynı iş parçacığı bir çağrıda döndürülen varsa `base` için `template` değil:  
  
```  
fnb12345  
```  
  
 FNA12345 mevcut değilse döndürülen sonraki yeniden adıdır:  
  
```  
fna12345  
```  
  
 `_mktemp`en fazla 26 benzersiz dosya adları için temel ve şablon değerleri verilen herhangi bir bileşimini oluşturabilirsiniz. Bu nedenle, FNZ12345 son benzersiz dosya adıdır `_mktemp` için oluşturabilirsiniz `base` ve `template` Bu örnekte kullanılan değerler.  
  
 Hata durumunda, `errno` ayarlanır. Varsa `template` biçimi geçersiz (örneğin, 6 daha az X'lerin), `errno` ayarlanır `EINVAL`. Varsa `_mktemp` tüm 26 olası dosya adları zaten var olduğundan, benzersiz bir ad oluşturamıyor `_mktemp` şablonu boş bir dize olarak ayarlar ve döndürür `EEXIST`.  
  
 C++'da, bu işlevlerin daha yeni, güvenli ortaklarınıza çağırma şablon aşırı yüklemeleri bu işlevler vardır. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_mktemp`|\<io.h >|  
|`_wmktemp`|\<io.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_getpid](../../c-runtime-library/reference/getpid.md)   
 [_kurulum Aç, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)