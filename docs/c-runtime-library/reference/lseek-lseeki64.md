---
title: _lseek, _lseeki64 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _lseeki64
- _lseek
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
- _lseeki64
- _lseek
- lseeki64
dev_langs:
- C++
helpviewer_keywords:
- lseek function
- _lseek function
- _lseeki64 function
- lseeki64 function
- file pointers [C++], moving
- seek file pointers
ms.assetid: aba8a768-d40e-48c3-b38e-473dbd782f93
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e9b711af0b5f8c5aec24ccfa4e395951b1caf302
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 02/14/2018
---
# <a name="lseek-lseeki64"></a>_lseek, _lseeki64
Dosya işaretçisini belirtilen konuma taşır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      long _lseek(  
   int fd,  
   long offset,  
   int origin   
);  
__int64 _lseeki64(  
   int fd,  
   __int64 offset,  
   int origin   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fd`  
 Açık olan bir dosyaya başvuruda bulunan dosya tanımlayıcısı.  
  
 uzaklık  
 Bayt sayısı *kaynak*.  
  
 *Kaynak*  
 Başlangıç konumu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_lseek` uzaklık, dosyanın yeni konumunu başlangıçtan itibaren bayt cinsinden döndürür. `_lseeki64` uzaklık bir 64-bit tamsayı olarak döndürür. İşlev L hatayı belirtmek için-1 döndürür. Hatalı dosya tanımlayıcısı veya değeri gibi geçersiz bir parametre aktarılırsa *kaynak* geçersiz veya tarafından belirtilen konumdaki *uzaklık* olan dosya başlamadan önce geçersiz bir parametre işleyicidir bölümünde açıklandığı gibi çağrılan [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için yürütülmesine izin veriliyorsa, bu işlevler kümesi `errno` için `EBADF` ve -1 M döndürür. Cihazlarda (Terminal ve yazıcılar gibi) aramayı kuramadığı dönüş değeri tanımlanmamıştır.  
  
 Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `_lseek` İşlevi ile ilişkili dosya işaretçisini taşır `fd` yeni bir konuma *uzaklık* baytlar *kaynak*. Dosyanın sonraki işlemi yeni konumda oluşur. *Kaynak* bağımsız değişkeni Stdio.h içinde tanımlanan sabitlerden biri olması gerekir.  
  
 `SEEK_SET`  
 Dosya başlangıcı.  
  
 `SEEK_CUR`  
 Dosya işaretçisini geçerli konumu.  
  
 `SEEK_END`  
 Dosya sonu.  
  
 Kullanabileceğiniz `_lseek` işaretçi bir dosya veya dosya ötesinde herhangi bir yere yeniden konumlandırmak için.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_lseek`|\<io.h >|  
|`_lseeki64`|\<io.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_lseek.c  
/* This program first opens a file named lseek.txt.  
 * It then uses _lseek to find the beginning of the file,  
 * to find the current position in the file, and to find  
 * the end of the file.  
 */  
  
#include <io.h>  
#include <fcntl.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
int main( void )  
{  
   int fh;  
   long pos;               /* Position of file pointer */  
   char buffer[10];  
  
   _sopen_s( &fh, "crt_lseek.c_input", _O_RDONLY, _SH_DENYNO, 0 );  
  
   /* Seek the beginning of the file: */  
   pos = _lseek( fh, 0L, SEEK_SET );  
   if( pos == -1L )  
      perror( "_lseek to beginning failed" );  
   else  
      printf( "Position for beginning of file seek = %ld\n", pos );  
  
   /* Move file pointer a little */  
    _read( fh, buffer, 10 );  
  
   /* Find current position: */  
   pos = _lseek( fh, 0L, SEEK_CUR );  
   if( pos == -1L )  
      perror( "_lseek to current position failed" );  
   else  
      printf( "Position for current position seek = %ld\n", pos );  
  
   /* Set the end of the file: */  
   pos = _lseek( fh, 0L, SEEK_END );  
   if( pos == -1L )  
      perror( "_lseek to end failed" );  
   else  
      printf( "Position for end of file seek = %ld\n", pos );  
  
   _close( fh );  
}  
```  
  
## <a name="input-crtlseekcinput"></a>Input: crt_lseek.c_input  
  
```  
Line one.  
Line two.  
Line three.  
Line four.  
Line five.  
```  
  
## <a name="output"></a>Çıkış  
  
```  
Position for beginning of file seek = 0  
Position for current position seek = 10  
Position for end of file seek = 57  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)   
 [fseek, _fseeki64](../../c-runtime-library/reference/fseek-fseeki64.md)   
 [_tell, _telli64](../../c-runtime-library/reference/tell-telli64.md)