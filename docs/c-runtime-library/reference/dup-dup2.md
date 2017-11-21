---
title: _dup, _dup2 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _dup
- _dup2
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
- _dup2
- _dup
dev_langs: C++
helpviewer_keywords:
- _dup2 function
- dup function
- file handles [C++], duplicating
- file handles [C++], reassigning
- dup2 function
- _dup function
ms.assetid: 4d07e92c-0d76-4832-a770-dfec0e7a0cfa
caps.latest.revision: "19"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f267ebf6526ed46cf3ef5670c6aeeb93a5a075e4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 10/24/2017
---
# <a name="dup-dup2"></a>_dup, _dup2
Açık bir dosya için ikinci bir dosya tanımlayıcısı oluşturur (`_dup`), veya bir dosya tanımlayıcısı yeniden atar (`_dup2`).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _dup(   
   int fd   
);  
int _dup2(   
   int fd1,  
   int fd2   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fd`, `fd1`  
 Dosyayı açmak için başvuran dosya tanımlayıcıları.  
  
 `fd2`  
 Herhangi dosya tanımlayıcısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_dup`Yeni bir dosya tanımlayıcısı döndürür. `_dup2`başarılı olduğunu belirtmek için 0 değerini döndürür. Bir hata oluşursa, her işlev dönüşleri -1 ve kümelerini `errno` için `EBADF` dosya tanımlayıcısı geçersizse veya için `EMFILE` hiçbir daha fazla dosya tanımlayıcıları varsa. Geçersiz dosya tanımlayıcısı söz konusu olduğunda, işlevi de geçersiz parametre işleyicisi açıklandığı gibi çağırır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).  
  
 Bunlar ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_dup` Ve `_dup2` işlevler şu anda açık bir dosyayla ikinci bir dosya tanımlayıcısı ilişkilendirin. Bu işlevler için gibi bir önceden tanımlanmış dosya tanımlayıcısı ilişkilendirmek için kullanılan `stdout`, farklı bir dosya ile. Dosya işlemleri ya da dosya tanımlayıcısı kullanılarak gerçekleştirilen kullanılabilir. Dosya için izin verilen erişim türü yeni bir açıklayıcısı oluşturma işlemi etkilenmez. `_dup`verilen dosya için bir sonraki kullanılabilir dosya tanımlayıcısı döndürür. `_dup2`zorlar `fd2` aynı dosyada başvurmak için `fd1`. Varsa `fd2` ilişkili açık bir dosyayı çağrısı zaman bu dosyayı kapalı.  
  
 Her ikisi de `_dup` ve `_dup2` dosya tanımlayıcıları parametre olarak kabul edin. Bir akış geçirmek için `(FILE *)` kullanın ya da bu işlevler için [_fileno](../../c-runtime-library/reference/fileno.md). `fileno` Yordamı şu anda belirtilen akışa ile ilişkili dosya tanımlayıcısı döndürür. Aşağıdaki örnekte nasıl ilişkilendirileceğini gösterir `stderr` (olarak tanımlanan `FILE` `*` Stdio.h içinde) ile bir dosya tanımlayıcısı:  
  
```  
int cstderr = _dup( _fileno( stderr ));  
```  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_dup`|\<io.h >|  
|`_dup2`|\<io.h >|  
  
 Konsol desteklenmeyen [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar. Konsol ile ilişkili standart akış tanıtıcıları —`stdin`, `stdout`, ve `stderr`— C çalışma zamanı işlevleri de kullanabilmek için önce yeniden yönlendirilmesi gerekiyor [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] uygulamalar. Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_dup.c  
// This program uses the variable old to save  
// the original stdout. It then opens a new file named  
// DataFile and forces stdout to refer to it. Finally, it  
// restores stdout to its original state.  
//  
  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int old;  
   FILE *DataFile;  
  
   old = _dup( 1 );   // "old" now refers to "stdout"   
                      // Note:  file descriptor 1 == "stdout"   
   if( old == -1 )  
   {  
      perror( "_dup( 1 ) failure" );  
      exit( 1 );  
   }  
   _write( old, "This goes to stdout first\n", 26 );  
   if( fopen_s( &DataFile, "data", "w" ) != 0 )  
   {  
      puts( "Can't open file 'data'\n" );  
      exit( 1 );  
   }  
  
   // stdout now refers to file "data"   
   if( -1 == _dup2( _fileno( DataFile ), 1 ) )  
   {  
      perror( "Can't _dup2 stdout" );  
      exit( 1 );  
   }  
   puts( "This goes to file 'data'\n" );  
  
   // Flush stdout stream buffer so it goes to correct file   
   fflush( stdout );  
   fclose( DataFile );  
  
   // Restore original stdout   
   _dup2( old, 1 );  
   puts( "This goes to stdout\n" );  
   puts( "The file 'data' contains:" );  
   _flushall();  
   system( "type data" );  
}  
```  
  
```Output  
This goes to stdout first  
This goes to stdout  
  
The file 'data' contains:  
This goes to file 'data'  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_kurulum Aç, _wopen](../../c-runtime-library/reference/open-wopen.md)