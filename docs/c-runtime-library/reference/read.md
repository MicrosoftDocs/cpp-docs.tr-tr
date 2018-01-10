---
title: _microsoft | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _read
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
f1_keywords: _read
dev_langs: C++
helpviewer_keywords:
- data [CRT]
- _read function
- read function
- data [C++], reading
- reading data [C++]
- files [C++], reading
ms.assetid: 2ce9c433-57ad-47fe-9ac1-4a7d4c883d30
caps.latest.revision: "15"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0c55e2607a706648c818fc94e73197756470110c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="read"></a>_read

Bir dosyadan veri okur.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _read(  
   int fd,  
   void *buffer,  
   unsigned int count   
);  
```  
  
### <a name="parameters"></a>Parametreler  

*FD*  
Açık olan dosyaya başvuran dosya tanımlayıcısı.  
  
*Arabellek*  
Verileri için depolama konumu.  
  
*sayısı*  
En fazla bayt sayısı.  
  
## <a name="return-value"></a>Dönüş Değeri  

`_read`hangi küçük olabilir, okunan bayt sayısını döndürür daha *sayısı* varsa daha az *sayısı* bayt sol dosyasında veya dosyayı metin modunda açtıysanız, bu durumda her satır başı satır çifti akış. `\r\n` tek satır besleme karakterle değiştirilir `\n`. Yalnızca tek satır besleme karakter dönüş değeri sayılır. Değiştirilen dosya işaretçisini etkilemez.  
  
Dosya sonu okumak işlevi çalışırsa, 0 döndürür. Varsa *fd* olduğundan geçerli değil, dosya okuma için açık değil veya dosyanın kilitli, açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için ayarlar ve işlev dönüşleri -1 yürütülmesine izin veriliyorsa `errno` için `EBADF`.  
  
Varsa *arabellek* olan **NULL**, geçersiz parametre işleyicisi çağrılır. Devam etmek için yürütülmesine izin veriliyorsa, işlevi -1 döndürür ve `errno` ayarlanır `EINVAL`.  
  
Bu ve diğer dönüş kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  

`_read` İşlevi okur en fazla *sayısı* baytlara *arabellek* ilişkili dosyasından *fd*. Belirtilen dosya ile ilişkili dosya işaretçisini geçerli konumunu okuma işlemi başlar. Okuma işleminden sonra sonraki okunmamış karaktere dosya işaretçisi işaret eder.  
  
Dosya metin modunda açıldıysa, okuma ne zaman sona erer `_read` bir dosya sonu göstergesi olarak kabul edilir bir CTRL + Z karakter karşılaşır. Kullanım [_lseek](../../c-runtime-library/reference/lseek-lseeki64.md) dosya sonu göstergesi temizleyin.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`_read`|\<io.h >|  
  
Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Kitaplıklar  

Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```C  
// crt_read.c  
/* This program opens a file named crt_read.txt  
 * and tries to read 60,000 bytes from  
 * that file using _read. It then displays the  
 * actual number of bytes read.  
 */  
  
#include <fcntl.h>      /* Needed only for _O_RDWR definition */  
#include <io.h>  
#include <stdlib.h>  
#include <stdio.h>  
#include <share.h>  
  
char buffer[60000];  
  
int main( void )  
{  
   int fh;  
   unsigned int nbytes = 60000, bytesread;  
  
   /* Open file for input: */  
   if( _sopen_s( &fh, "crt_read.txt", _O_RDONLY, _SH_DENYNO, 0 ) )  
   {  
      perror( "open failed on input file" );  
      exit( 1 );  
   }  
  
   /* Read in input: */  
   if( ( bytesread = _read( fh, buffer, nbytes ) ) <= 0 )  
      perror( "Problem reading file" );  
   else  
      printf( "Read %u bytes from file\n", bytesread );  
  
   _close( fh );  
}  
```  
  
### <a name="input-crtreadtxt"></a>Giriş: crt_read.txt  
  
```  
Line one.  
Line two.  
```  
  
### <a name="output"></a>Çıkış  
  
```  
Read 19 bytes from file  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  

[Düşük düzey g/ç](../../c-runtime-library/low-level-i-o.md)   
[_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
[fread](../../c-runtime-library/reference/fread.md)   
[_kurulum Aç, _wopen](../../c-runtime-library/reference/open-wopen.md)   
[_write](../../c-runtime-library/reference/write.md)
