---
title: _tempnam, _wtempnam, tmpnam, _wtmpnam | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wtempnam
- _wtmpnam
- tmpnam
- _tempnam
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
- wtempnam
- _wtmpnam
- wtmpnam
- tmpnam
- _wtempnam
- _tempnam
dev_langs:
- C++
helpviewer_keywords:
- wtempnam function
- file names [C++], creating temporary
- _tempnam function
- ttmpnam function
- tmpnam function
- tempnam function
- wtmpnam function
- temporary files, creating
- file names [C++], temporary
- _ttmpnam function
- _wtmpnam function
- _wtempnam function
ms.assetid: 3ce75f0f-5e30-42a6-9791-8d7cbfe70fca
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29b0f7f645bd23c04e9d9f31dc914e29f7a048cb
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="tempnam-wtempnam-tmpnam-wtmpnam"></a>_tempnam, _wtempnam, tmpnam, _wtmpnam
Geçici dosyaları oluşturmak için kullanabileceğiniz adları oluşturun. Bu işlevlerin bazıları daha güvenli sürümleri kullanılabilir; bkz: [tmpnam_s, _wtmpnam_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
char *_tempnam(  
   const char *dir,  
   const char *prefix   
);  
wchar_t *_wtempnam(  
   const wchar_t *dir,  
   const wchar_t *prefix   
);  
char *tmpnam(  
   char *str   
);  
wchar_t *_wtmpnam(  
   wchar_t *str   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `prefix`  
 Bekletilen tarafından döndürülen adlarına olacaktır dize `_tempnam`.  
  
 `dir`  
 Dosya adında hiçbir TMP ortam değişkeni ise veya TMP geçerli bir dizin değil ise kullanılan yol.  
  
 `str`  
 Oluşturulan ad tutacak ve işlev tarafından döndürülen adıyla aynı olacak işaretçi. Bu, oluşturulan adı kaydetmek için kullanışlı bir yoludur.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Bu işlevlerin her biri bir işaretçi oluşturulan adı döndürür veya `NULL` bir hata olduğunda. Hata meydana gelebilir dener birden fazla `TMP_MAX` (STDIO bakın. H) aramaları `tmpnam` veya kullanıyorsanız `_tempnam` ve TMP ortam değişkeni hem de belirtilen geçersiz dizin adı `dir` parametresi.  
  
> [!NOTE]
>  Tarafından döndürülen işaretçileri `tmpnam` ve `_wtmpnam` noktası için statik iç arabellek. [Ücretsiz](../../c-runtime-library/reference/free.md) bu işaretçileri ayırması için çağrılmamalıdır. `free` işaretçiler tarafından ayrılmış için çağrılması gereken `_tempnam` ve `_wtempnam`.  
  
## <a name="remarks"></a>Açıklamalar  
 Bu işlevlerin her biri şu anda var olmayan bir dosya adını döndürür. `tmpnam` Geçerli çalışma dizini içinde benzersiz bir ad döndürür ve `_tempnam` geçerli dışında bir dizinde benzersiz bir ad oluşturmanıza olanak sağlar. Bir dosya adı bekletilen bir ters eğik çizgi ve \fname21 gibi hiçbir yol bilgileriyle olduğunda bu adın geçerli çalışma dizini için geçerli olduğunu belirttiğinden unutmayın.  
  
 İçin `tmpnam`, bu oluşturulan dosya adı depolayabilir `str`. Varsa `str` olan `NULL`, ardından `tmpnam` sonucu bir iç statik arabellek bırakır. Bu nedenle yapılan sonraki çağrılar bu değer yok. Tarafından oluşturulan adı `tmpnam` bir program tarafından oluşturulan dosya adının ve ilk çağrısından sonra oluşan `tmpnam`, temel 32 sıralı numaraları için bir dosya uzantısı (.1-.vvu olduğunda `TMP_MAX` STDIO içinde. H 32.767 ise).  
  
 `_tempnam` benzersiz bir dosya adı aşağıdaki kurallara göre seçilen bir dizin oluşturur:  
  
-   TMP ortam değişkeni tanımlı ve geçerli dizin adına ayarlayın, benzersiz dosya adları TMP tarafından belirtilen dizin için oluşturulur.  
  
-   TMP ortam değişkeni tanımlanmamışsa, ya da mevcut değil, bir dizin adını ayarlarsanız `_tempnam` kullanacağı `dir` parametre olarak kendisi için bu oluşturacağını benzersiz adlar yolu.  
  
-   TMP ortam değişkeni tanımlanmamışsa veya var olmayan bir dizin adı için ayarlandıysa ve varsa `dir` ya `NULL` veya var olmayan bir dizin adını ayarlamak `_tempnam` gene için geçerli çalışma dizini kullanır benzersiz adlar oranı. Şu anda, her iki TMP ve `dir` var olmadığından, dizin adlarını belirtin `_tempnam` işlev çağrısı başarısız olur.  
  
 Tarafından döndürülen adı `_tempnam` bir birleşimi olacaktır `prefix` ve benzersiz bir dosya adı için belirtilen dizin oluşturmak için birleştirir bir sıra numarası. `_tempnam` hiçbir uzantılı dosya adları oluşturur. `_tempnam` kullanan [malloc](../../c-runtime-library/reference/malloc.md) filename; alan ayırmak için artık gerekli olmadığında bu alanı boşaltma için sorumlu bir programdır.  
  
 `_tempnam` ve `tmpnam` otomatik olarak çok baytlı karakter sıralarının OEM kod sayfasına göre algılamayı tanıtıcı çok baytlı karakter dizesi bağımsız değişken olarak uygun alınan işletim sisteminden. `_wtempnam` bir joker karakter sürümü `_tempnam`; değişkenler ve dönüş değerini `_wtempnam` joker karakter dizelerdir. `_wtempnam` ve `_tempnam` durumlar dışında aynı şekilde davranır `_wtempnam` çok baytlı karakter dizeleri işlemez. `_wtmpnam` bir joker karakter sürümü `tmpnam`; bağımsız değişkeni ve dönüş değeri `_wtmpnam` joker karakter dizelerdir. `_wtmpnam` ve `tmpnam` durumlar dışında aynı şekilde davranır `_wtmpnam` çok baytlı karakter dizeleri işlemez.  
  
 Varsa `_DEBUG` ve `_CRTDBG_MAP_ALLOC` tanımlanan `_tempnam` ve `_wtempnam` yapılan çağrılar tarafından değiştirilen [_tempnam_dbg ve _wtempnam_dbg](../../c-runtime-library/reference/tempnam-dbg-wtempnam-dbg.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ttmpnam`|`tmpnam`|`tmpnam`|`_wtmpnam`|  
|`_ttempnam`|`_tempnam`|`_tempnam`|`_wtempnam`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_tempnam`|\<stdio.h >|  
|`_wtempnam`, `_wtmpnam`|\<stdio.h > veya \<wchar.h >|  
|`tmpnam`|\<stdio.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_tempnam.c  
// compile with: /W3  
// This program uses tmpnam to create a unique filename in the  
// current working directory, then uses _tempnam to create   
// a unique filename with a prefix of stq.   
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char* name1 = NULL;  
   char* name2 = NULL;  
  
   // Create a temporary filename for the current working directory:   
   if( ( name1 = tmpnam( NULL ) ) != NULL ) // C4996  
   // Note: tmpnam is deprecated; consider using tmpnam_s instead  
      printf( "%s is safe to use as a temporary file.\n", name1 );  
   else  
      printf( "Cannot create a unique filename\n" );  
  
   // Create a temporary filename in temporary directory with the  
   // prefix "stq". The actual destination directory may vary  
   // depending on the state of the TMP environment variable and  
   // the global variable P_tmpdir.     
  
   if( ( name2 = _tempnam( "c:\\tmp", "stq" ) ) != NULL )  
      printf( "%s is safe to use as a temporary file.\n", name2 );   
   else  
      printf( "Cannot create a unique filename\n" );  
  
   // When name2 is no longer needed :     
   if(name2)  
     free(name2);  
  
}  
```  
  
```Output  
\s1gk. is safe to use as a temporary file.  
C:\DOCUME~1\user\LOCALS~1\Temp\2\stq2 is safe to use as a temporary file.  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile](../../c-runtime-library/reference/tmpfile.md)   
 [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md)