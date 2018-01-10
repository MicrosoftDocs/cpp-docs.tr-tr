---
title: _mktemp_s, _wmktemp_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
apitype: DLLExport
f1_keywords:
- wmktemp_s
- mktemp_s
- _mktemp_s
- _wmktemp_s
dev_langs: C++
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
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9515212418b4bd4e8d9957254b2fafaf451a3adc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="mktemps-wmktemps"></a>_mktemp_s, _wmktemp_s
Benzersiz bir dosya adı oluşturur. Sürümleri bunlar [_mktemp, _wmktemp](../../c-runtime-library/reference/mktemp-wmktemp.md) açıklandığı gibi güvenlik geliştirmeleri ile [CRT'deki güvenlik özellikleri](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
errno_t _mktemp_s(  
   char *template,  
   size_t sizeInChars  
);  
errno_t _wmktemp_s(  
   wchar_t *template,  
   size_t sizeInChars  
);  
template <size_t size>  
errno_t _mktemp_s(  
   char (&template)[size]  
); // C++ only  
template <size_t size>  
errno_t _wmktemp_s(  
   wchar_t (&template)[size]  
); // C++ only  
```  
  
#### <a name="parameters"></a>Parametreler  
 `template`  
 Dosya adı deseni.  
  
 `sizeInChars`  
 Tek baytlı karakter arabellek boyutunu `_mktemp_s`; geniş içinde karakterleri `_wmktemp_s`, null Sonlandırıcı dahil olmak üzere.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her ikisi de başarılı sıfır döndürür; hatasında bir hata kodu.  
  
### <a name="error-conditions"></a>Hata koşulları  
  
|`template`|`sizeInChars`|**dönüş değeri**|**şablonda yeni değer**|  
|----------------|-------------------|----------------------|-------------------------------|  
|`NULL`|tüm|`EINVAL`|`NULL`|  
|Hatalı biçimde (bkz `Remarks` bölümü doğru biçim için)|tüm|`EINVAL`|Boş dize|  
|tüm|< = sayısı X'lerin|`EINVAL`|Boş dize|  
  
 Yukarıdaki hata koşullardan herhangi biri meydana gelirse, geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlevleri döndürür `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_mktemp_s` İşlev değiştirerek benzersiz bir dosya adı oluşturur `template` bağımsız değişkeni, böylece, çağrısından sonra `template` işaretçinin işaret yeni dosya adı içeren bir dize. `_mktemp_s`çok baytlı karakter sıralarının şu anda kullanımda birden çok baytlı kod sayfasına göre çalışma zamanı sistem tarafından algılamayı çok baytlı karakter dizesi bağımsız değişkenleri uygun şekilde otomatik olarak yönetir. `_wmktemp_s`bir joker karakter sürümü `_mktemp_s`; bağımsız değişkeni `_wmktemp_s` bir joker karakter dizesidir. `_wmktemp_s`ve `_mktemp_s` aynı şekilde Aksi takdirde, dışında davranır `_wmktemp_s` çok baytlı karakter dizeleri işlemez.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tmktemp_s`|`_mktemp_s`|`_mktemp_s`|`_wmktemp_s`|  
  
 `template` Bağımsız değişkenini içeriyor formun `baseXXXXXX`, burada `base` sağladığınız yeni dosya adı parçası ve her X tarafından sağlanan bir karakter için bir yer tutucudur `_mktemp_s`. Her yer tutucu karakter `template` bir büyük harf x olmalıdır `_mktemp_s` korur `base` ve ilk sonunda X alfabetik bir karakter ile değiştirir. `_mktemp_s`Aşağıdaki sondaki değiştirir X'lerin beş basamaklı değerle; Bu değer, işlem, veya birden çok iş parçacıklı programlar çağıran iş parçacığı arama tanımlayan benzersiz bir sayıdır.  
  
 Her başarılı çağrısı `_mktemp_s` değiştirir `template`. Aynı işlem ya da aynı iş parçacığı sonraki her çağrıda `template` bağımsız değişkeni, `_mktemp_s` tarafından döndürülen adlarıyla dosya adları için denetimleri `_mktemp_s` önceki çağrılarında. Bir verilen ad için hiçbir dosya varsa, `_mktemp_s` o adını döndürür. Tüm adlar, döndürülen için dosyalar varsa `_mktemp_s` kullanılan sonraki kullanılabilir küçük harf, sırayla 'a' ile 'z' ile daha önce döndürülen adı alfasayısal bir karakter değiştirerek yeni bir ad oluşturur. Örneğin, varsa `base` değil:  
  
```  
fn  
```  
  
 tarafından sağlanan beş basamaklı değeri `_mktemp_s` 12345, ilk döndürülen adıdır:  
  
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
  
 `_mktemp_s`en fazla 26 benzersiz dosya adları için temel ve şablon değerleri verilen herhangi bir bileşimini oluşturabilirsiniz. Bu nedenle, FNZ12345 son benzersiz dosya adıdır `_mktemp_s` için oluşturabilirsiniz `base` ve `template` Bu örnekte kullanılan değerler.  
  
 C++'da, bu işlevler kullanılarak şablon aşırı yüklemeleri tarafından basitleştirilmiştir; aşırı arabellek uzunluğu otomatik olarak Infer (boyutu bağımsız değişkeniyle belirtme ihtiyacını ortadan) ve bunlar otomatik olarak yeni, güvenli dekiler ile daha eski, güvenli olmayan işlevleri değiştirebilirsiniz. Daha fazla bilgi için bkz: [güvenli şablon aşırı yüklemeler](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_mktemp_s`|\<io.h >|  
|`_wmktemp_s`|\<io.h > veya \<wchar.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
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
  
## <a name="sample-output"></a>Örnek Çıktı  
  
```  
Unique filename is fna03188  
Unique filename is fnb03188  
Unique filename is fnc03188  
Unique filename is fnd03188  
Unique filename is fne03188  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [_getpid](../../c-runtime-library/reference/getpid.md)   
 [_kurulum Aç, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)