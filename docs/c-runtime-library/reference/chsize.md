---
title: _chsize | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _chsize
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
f1_keywords: _chsize
dev_langs: C++
helpviewer_keywords:
- size
- _chsize function
- size, changing file
- files [C++], changing size
- chsize function
ms.assetid: b3e881c5-7b27-4837-a3d4-c51591ab10ff
caps.latest.revision: "21"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9c48c9978650dc88ff2579a2838faf9bcb02cefa
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="chsize"></a>_chsize
Dosyasının boyutu değişir. Daha güvenli bir sürümünü kullanılabilir; bkz: [_chsize_s](../../c-runtime-library/reference/chsize-s.md).  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _chsize(   
   int fd,  
   long size   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `fd`  
 Açık olan bir dosyaya başvuruda bulunan dosya tanımlayıcısı.  
  
 `size`  
 Yeni dosyanın bayt cinsinden uzunluğu.  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_chsize`Dosya boyutu başarıyla değiştirilirse 0 değerini döndürür. Dönüş değeri -1, bir hata gösterir: `errno` ayarlanır `EACCES` belirtilen dosya erişime karşı çok kilitliyse `EBADF` belirtilen dosya salt okunur ise veya tanımlayıcısı geçersiz `ENOSPC` boşluk cihaz veya bırakılırsa`EINVAL` varsa `size` sıfırdan küçüktür.  
  
 Bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md) bu ve diğer hakkında daha fazla bilgi için dönüş kodları.  
  
## <a name="remarks"></a>Açıklamalar  
 `_chsize` İşlevi genişletir veya ilişkili dosya kesen `fd` tarafından belirtilen uzunluğa `size`. Dosya yazma izin veren bir modda açık olması gerekir. Boş karakterler ('\0') dosya genişletilmişse eklenir. Dosya kesilirse, dosyanın özgün uzunluğu kısaltılmış dosyasının sonuna tüm veriler kaybolur.  
  
 Bu işlev parametrelerini doğrular. Varsa `size` sıfırdan küçüktür veya `fd` hatalı dosya tanımlayıcısı açıklandığı gibi geçersiz parametre işleyicisi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|İsteğe bağlı üstbilgi|  
|-------------|---------------------|---------------------|  
|`_chsize`|\<io.h >|\<errno.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_chsize.c  
// This program uses _filelength to report the size  
// of a file before and after modifying it with _chsize.  
  
#include <io.h>  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <stdio.h>  
#include <share.h>  
  
int main( void )  
{  
   int fh, result;  
   unsigned int nbytes = BUFSIZ;  
  
   // Open a file   
   if( _sopen_s( &fh, "data", _O_RDWR | _O_CREAT, _SH_DENYNO,  
                 _S_IREAD | _S_IWRITE ) == 0 )  
   {  
      printf( "File length before: %ld\n", _filelength( fh ) );  
      if( ( result = _chsize( fh, 329678 ) ) == 0 )  
         printf( "Size successfully changed\n" );  
      else  
         printf( "Problem in changing the size\n" );  
      printf( "File length after:  %ld\n", _filelength( fh ) );  
      _close( fh );  
   }  
}  
```  
  
```Output  
File length before: 0  
Size successfully changed  
File length after:  329678  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Dosya işleme](../../c-runtime-library/file-handling.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)