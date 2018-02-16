---
title: _locking | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _locking
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
- _locking
dev_langs:
- C++
helpviewer_keywords:
- locking function
- bytes [C++], locking file
- files [C++], locking bytes
- files [C++], locking
- _locking function
ms.assetid: 099aaac1-d4ca-4827-aed6-24dff9844150
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 0acd33e3f33077dafee9bd6c4892a17b42e7afe0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="locking"></a>_locking
Kilitler veya bir dosyanın bayt kilidini açar.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      int _locking(  
   int fd,  
   int mode,  
   long nbytes   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fd`  
 Dosya tanımlayıcısı.  
  
 *mode*  
 Eylem kilitleme.  
  
 *nbytes*  
 Kilitlenecek bayt sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_locking` Başarılı olursa 0 döndürür. Dönüş değeri-1 hata, bu durumda gösteriyor [errno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) aşağıdaki değerlerden birine ayarlayın.  
  
 `EACCES`  
 Kilitleme ihlali (zaten kilitli veya kilidi dosyası).  
  
 `EBADF`  
 Geçersiz dosya tanımlayıcısı.  
  
 `EDEADLOCK`  
 Kilit ihlali. Ne zaman döndürülen `_LK_LOCK` veya `_LK_RLCK` bayrağı belirtilir ve 10 denemeden sonra dosya kilitlenemez.  
  
 `EINVAL`  
 Geçersiz bağımsız değişken için verilen `_locking`.  
  
 Geçersiz dosya açıklayıcısı gibi hatalı bir parametre nedeniyle başarısız olması durumunda geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_locking` İşlevi kilitler veya kilidini açar *nbytes* tarafından belirtilen dosya bayt `fd`. Bir dosyada baytları kilitleme erişimi başka işlemler tarafından bu bayt engeller. Tüm kilitlenmesi veya kilidinin kaldırılması dosya işaretçisini geçerli konumunda başlayan ve sonraki geçer *nbytes* bayt sayısı. Kilit bayt mümkündür dosyanın sonunu geçti.  
  
 *mod* Locking.h içinde tanımlanan aşağıdaki bildirim sabitlerden biri olması gerekir.  
  
 `_LK_LOCK`  
 Belirtilen bayt kilitler. Bayt kilitlenemez, programın yeniden 1 saniye sonra hemen çalışır. 10 denemeden sonra bayt kilitlenemez varsa, sabit bir hata döndürür.  
  
 `_LK_NBLCK`  
 Belirtilen bayt kilitler. Bayt kilitlenemez, sabit bir hata döndürür.  
  
 `_LK_NBRLCK`  
 Aynı `_LK_NBLCK`.  
  
 `_LK_RLCK`  
 Aynı `_LK_LOCK`.  
  
 `_LK_UNLCK`  
 Daha önce kilitlendiğinden gerekir belirtilen bayt kilidini açar.  
  
 Çakışmaması birden çok bölgeye dosyasının kilitlenebilir. Kilidi açılıyor bir bölge önceden kilitlendiğinden gerekir. `_locking` bitişik bölgeler birleştirmez; iki kilitli bölgeler bitişik varsa, her bölge ayrı olarak kilidinin açılması gerekir. Bölgeler yalnızca kısa bir süre kilitli olmalıdır ve bir dosyayı kapatma veya program çıkmadan önce kilidinin.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_locking`|\<io.h > ve \<sys/locking.h >|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_locking.c  
/* This program opens a file with sharing. It locks  
 * some bytes before reading them, then unlocks them. Note that the  
 * program works correctly only if the file exists.  
 */  
  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <sys/locking.h>  
#include <share.h>  
#include <fcntl.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <io.h>  
  
int main( void )  
{  
   int  fh, numread;  
   char buffer[40];  
  
   /* Quit if can't open file or system doesn't   
    * support sharing.   
    */  
   errno_t err = _sopen_s( &fh, "crt_locking.txt", _O_RDONLY, _SH_DENYNO,   
                          _S_IREAD | _S_IWRITE );  
   printf( "%d %d\n", err, fh );  
   if( err != 0 )  
      exit( 1 );  
  
   /* Lock some bytes and read them. Then unlock. */  
   if( _locking( fh, LK_NBLCK, 30L ) != -1 )  
   {  
      long lseek_ret;  
      printf( "No one can change these bytes while I'm reading them\n" );  
      numread = _read( fh, buffer, 30 );  
      buffer[30] = '\0';  
      printf( "%d bytes read: %.30s\n", numread, buffer );  
      lseek_ret = _lseek( fh, 0L, SEEK_SET );  
      _locking( fh, LK_UNLCK, 30L );  
      printf( "Now I'm done. Do what you will with them\n" );  
   }  
   else  
      perror( "Locking failed\n" );  
  
   _close( fh );  
}  
```  
  
## <a name="input-crtlockingtxt"></a>Giriş: crt_locking.txt  
  
```  
The first thirty bytes of this file will be locked.  
```  
  
## <a name="sample-output"></a>Örnek Çıktı  
  
```  
No one can change these bytes while I'm reading them  
30 bytes read: The first thirty bytes of this  
Now I'm done. Do what you will with them  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)