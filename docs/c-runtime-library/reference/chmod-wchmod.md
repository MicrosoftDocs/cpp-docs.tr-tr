---
title: _chmod, _wchmod | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _chmod
- _wchmod
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
- api-ms-win-crt-filesystem-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _chmod
- _wchmod
- wchmod
dev_langs: C++
helpviewer_keywords:
- _chmod function
- wchmod function
- file permissions [C++]
- chmod function
- files [C++], changing permissions
- _wchmod function
ms.assetid: 92f7cb86-b3b0-4232-a599-b8c04a2f2c19
caps.latest.revision: "23"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9da654c37b79e9a5398968500f8150d82e4f022c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="chmod-wchmod"></a>_chmod, _wchmod
Dosya izni ayarlarını değiştirir.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int _chmod(   
   const char *filename,  
   int pmode   
);  
int _wchmod(   
   const wchar_t *filename,  
   int pmode   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `filename`  
 Varolan dosyanın adı.  
  
 `pmode`  
 Dosya izni ayarı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 İzni ayarı başarıyla değiştirilirse bu işlevler 0 döndürür. Dönüş değeri-1 hata gösterir. Belirtilen dosya bulunamadı, `errno` ayarlanır `ENOENT`; bir parametre geçersiz `errno` ayarlanır `EINVAL`.  
  
## <a name="remarks"></a>Açıklamalar  
 `_chmod` İşlevi tarafından belirtilen dosya izni ayarı değişiklikleri `filename`. Okuma ve yazma erişimi dosya izni ayarı denetler. Tamsayı ifade `pmode` birini veya her ikisini SYS\Stat.h tanımlanan aşağıdaki bildirim sabitleri içerir.  
  
 `_S_IWRITE`  
 Yazma izin verilir.  
  
 `_S_IREAD`  
 Okuma izin verilir.  
  
 `_S_IREAD | _S_IWRITE`  
 Okuma ve yazma izin verilir.  
  
 Her iki sabitleri verildiğinde, bunlar Bitsel ile katılan `OR` işleci ( `|` ). Yazma izni verilmedi, dosya salt okunurdur. Tüm dosyaları her zaman okunabilir olduğunu unutmayın; salt yazılır izin vermek mümkün değildir. Bu nedenle, modları `_S_IWRITE` ve `_S_IREAD | _S_IWRITE` eşdeğerdir.  
  
 `_wchmod`bir joker karakter sürümü `_chmod`; `filename` bağımsız değişkeni `_wchmod` bir joker karakter dizesidir. `_wchmod`ve `_chmod` Aksi takdirde aynı şekilde davranır.  
  
 Bu işlev parametrelerini doğrular. Varsa `pmode` bildirim sabitleri bir birleşimini değil veya başka bir kümesi içerir, sabitleri işlevi yalnızca bu yok sayar. Varsa `filename` olan `NULL`, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa `errno` ayarlanır `EINVAL` ve işlev -1 döndürür.  
  
### <a name="generic-text-routine-mappings"></a>Genel Metin Yordam Eşleşmeleri  
  
|Tchar.h yordamı|_UNICODE ve _MBCS tanımlanmaz|_MBCS tanımlanmış|_UNICODE tanımlanmış|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tchmod`|`_chmod`|`_chmod`|`_wchmod`|  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_chmod`|\<io.h >|\<sys/Types.h >, \<sys/stat.h >, \<errno.h >|  
|`_wchmod`|\<io.h > veya \<wchar.h >|\<sys/Types.h >, \<sys/stat.h >, \<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_chmod.c  
// This program uses _chmod to  
// change the mode of a file to read-only.  
// It then attempts to modify the file.  
//  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
// Change the mode and report error or success   
void set_mode_and_report(char * filename, int mask)  
{  
   // Check for failure   
   if( _chmod( filename, mask ) == -1 )  
   {  
      // Determine cause of failure and report.   
      switch (errno)  
      {  
         case EINVAL:  
            fprintf( stderr, "Invalid parameter to chmod.\n");  
            break;  
         case ENOENT:  
            fprintf( stderr, "File %s not found\n", filename );  
            break;  
         default:  
            // Should never be reached   
            fprintf( stderr, "Unexpected error in chmod.\n" );  
       }  
   }  
   else  
   {  
      if (mask == _S_IREAD)  
        printf( "Mode set to read-only\n" );  
      else if (mask & _S_IWRITE)  
        printf( "Mode set to read/write\n" );  
   }  
   fflush(stderr);  
}  
  
int main( void )  
{   
  
   // Create or append to a file.   
   system( "echo /* End of file */ >> crt_chmod.c_input" );  
  
   // Set file mode to read-only:   
   set_mode_and_report("crt_chmod.c_input ", _S_IREAD );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );  
  
   // Change back to read/write:   
   set_mode_and_report("crt_chmod.c_input ", _S_IWRITE );  
  
   system( "echo /* End of file */ >> crt_chmod.c_input " );   
}   
```  
  
```Output  
  
A line of text.  
  
```  
  
```Output  
  
      A line of text.Mode set to read-only  
Access is denied.  
Mode set to read/write  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [_access, _waccess](../../c-runtime-library/reference/access-waccess.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_fstat, _fstat32, _fstat64, _fstati64, _fstat32i64, _fstat64i32](../../c-runtime-library/reference/fstat-fstat32-fstat64-fstati64-fstat32i64-fstat64i32.md)   
 [_kurulum Aç, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_stat, _wstat işlevleri](../../c-runtime-library/reference/stat-functions.md)