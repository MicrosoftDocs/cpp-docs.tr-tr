---
title: ungetc, ungetwc | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- ungetwc
- ungetc
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
- _ungettc
- ungetwc
- ungetc
dev_langs: C++
helpviewer_keywords:
- ungetwc function
- ungettc function
- characters, pushing back onto stream
- _ungettc function
- ungetc function
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ba352160afb6dc4a429721cd7af61204f5ef79e1
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="ungetc-ungetwc"></a>ungetc, ungetwc
Bir karakter geri akışa iter.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int ungetc(  
   int c,  
   FILE *stream   
);  
wint_t ungetwc(  
   wint_t c,  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `c`  
 Edilmesini karakter.  
  
 `stream`  
 İşaretçi `FILE` yapısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı, bu işlevlerin her biri karakter bağımsız verir durumunda `c`. Varsa `c` geri gönderilir ya da hiçbir karakter okuyorsanız Giriş akışı değiştirilmemiştir ve `ungetc` döndürür `EOF`; `ungetwc` döndürür `WEOF`. Varsa `stream` olan `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `EOF` veya `WEOF` döndürülür ve `errno` ayarlanır `EINVAL`.  
  
 Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `ungetc` İşlevi iter karakter `c` geri üzerine `stream` ve dosya sonu göstergesi temizler. Akış okuma için açık olması gerekir. Bir sonraki üzerinde okuma işlemi `stream` ile başlayan `c`. Gönderme girişiminde `EOF` akışı kullanarak üzerine `ungetc` göz ardı edilir.  
  
 Karakter yerleştirilen tarafından akışta `ungetc` varsa silinebilir `fflush`, `fseek`, `fsetpos`, veya `rewind` karakter akıştan okunan önce çağrılır. Dosya konumu göstergesi karakterleri geri gönderilen önceki değerine sahip olacaktır. Akışa karşılık gelen harici depolama değiştirilmez. Başarılı bir üzerinde `ungetc` dosya konumu göstergesi bir metin akış karşı çağrıdır belirtilmeyen tüm kadar gönderilen geri karakterleri okuma veya atılır. Her başarılı `ungetc` çağrısı, dosya konumu göstergesi ikili akışın karşı indirildiği; değeri bir çağrıdan önce 0 ise, değer çağrısından sonra tanımlı değil.  
  
 Sonuçları öngörülemeyen varsa `ungetc` bir okuma veya dosya konumlandırma işlemi iki çağrılar arasında olmadan iki kez çağrılır. Çağrı sonra `fscanf`, çağrı `ungetc` sürece başka okuma işlemi başarısız olabilir (gibi `getc`) gerçekleştirilmiştir. Bunun nedeni, `fscanf` kendi kendini çağıran `ungetc`.  
  
 `ungetwc`bir joker karakter sürümü `ungetc`. Bununla birlikte, her üzerinde başarılı `ungetwc` bir metin veya İkili akış dosya konumu göstergesi değerini karşı çağrı belirtilmeyen tüm gönderilen geri karakterleri okuma veya atılan kadar.  
  
 Bu işlevler iş parçacığı ve yürütme sırasında hassas verileri kilitleyin. Kilitleme olmayan bir sürümü için bkz: [_ungetc_nolock, _ungetwc_nolock](../../c-runtime-library/reference/ungetc-nolock-ungetwc-nolock.md).  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|TCHAR.H yordamı|_UNICODE & _MBCS tanımlanmamış|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_ungettc`|`ungetc`|`ungetc`|`ungetwc`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`ungetc`|\<stdio.h >|  
|`ungetwc`|\<stdio.h > veya \<wchar.h >|  
  
 Konsol desteklenmeyen [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar. Konsol ile ilişkili standart akış tanıtıcıları —`stdin`, `stdout`, ve `stderr`— C çalışma zamanı işlevleri de kullanabilmek için önce yeniden yönlendirilmesi gerekiyor [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar. Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_ungetc.c  
// This program first converts a character  
// representation of an unsigned integer to an integer. If  
// the program encounters a character that is not a digit,  
// the program uses ungetc to replace it in the  stream.  
//  
  
#include <stdio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
   int result = 0;  
  
   // Read in and convert number:  
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )  
      result = result * 10 + ch - '0';    // Use digit.  
   if( ch != EOF )  
      ungetc( ch, stdin );                // Put nondigit back.  
   printf( "Number = %d\nNext character in stream = '%c'",   
            result, getchar() );  
}  
```  
  
```Output  
  
      521aNumber = 521  
Next character in stream = 'a'  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)