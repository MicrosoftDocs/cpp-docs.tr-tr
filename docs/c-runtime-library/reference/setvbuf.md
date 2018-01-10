---
title: setvbuf | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: setvbuf
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
f1_keywords: setvbuf
dev_langs: C++
helpviewer_keywords:
- controlling stream buffering
- stream buffering
- setvbuf function
ms.assetid: 6aa5aa37-3408-4fa0-992f-87f9f9c4baea
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 0855982627c60c51ec5753031ae932ffd430f024
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="setvbuf"></a>setvbuf
Akışı arabelleğe alma ve arabellek boyutunu denetler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int setvbuf(  
   FILE *stream,  
   char *buffer,  
   int mode,  
   size_t size   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stream`  
 İşaretçi `FILE` yapısı.  
  
 `buffer`  
 Kullanıcı tarafından ayrılan arabellek.  
  
 `mode`  
 Arabelleğe alma modu.  
  
 `size`  
 Bayt cinsinden arabellek boyutu. İzin verilen aralık: 2 < = `size` < = INT_MAX (2147483647). Dahili olarak, için sağlanan değer `size` 2 yakın katına yuvarlanır.  
  
## <a name="return-value"></a>Dönüş Değeri  
 Başarılı olursa 0 döndürür.  
  
 Varsa `stream` olan `NULL`, veya `mode` veya `size` olan geçerli bir değişiklik içinde geçersiz parametre işleyicisi, açıklandığı gibi çağrılır [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Devam etmek için bu işlev dönüşleri -1 ve kümelerini yürütülmesine izin veriliyorsa `errno` için `EINVAL`.  
  
 Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Açıklamalar  
 `setvbuf` İşlevi sağlar ve arabellek boyutu için her iki kez arabelleğe alma denetlemek program `stream`. `stream`açıldıktan sonra bir g/ç işlemi geçmemiştir açık bir dosyadan başvurmalıdır. Tarafından diziyi işaret için `buffer` olduğu sürece arabellek olarak kullanılan `NULL`, bu durumda `setvbuf` kullandığı otomatik olarak ayrılmış bir arabellek uzunluğu `size`/2 * 2 bayt.  
  
 Modu olmalıdır `_IOFBF`, `_IOLBF`, veya `_IONBF`. Varsa `mode` olan `_IOFBF` veya `_IOLBF`, ardından `size` arabellek boyutu kullanılır. Varsa `mode` olan `_IONBF`, akış arabellekten çıkarılan ve `size` ve `buffer` göz ardı edilir. İçin değerler `mode` ve anlamlarını şunlardır:  
  
 `_IOFBF`  
 Tam arabelleğe alma; diğer bir deyişle, `buffer` arabellek olarak kullanılan ve `size` arabellek boyutu kullanılır. Varsa `buffer` olan `NULL`, otomatik olarak ayrılmış bir arabellek `size` bayt uzunluğundadır kullanılır.  
  
 `_IOLBF`  
 Bazı sistemler için bu satırı arabelleğe almayı sağlar. Ancak, Win32 için aynı davranıştır `_IOFBF` -tam arabelleğe alma.  
  
 `_IONBF`  
 Hiçbir arabellek kullanılan, ne olursa olsun, `buffer` veya `size`.  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|`setvbuf`|\<stdio.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_setvbuf.c  
// This program opens two streams: stream1  
// and stream2. It then uses setvbuf to give stream1 a  
// user-defined buffer of 1024 bytes and stream2 no buffer.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   char buf[1024];  
   FILE *stream1, *stream2;  
  
   if( fopen_s( &stream1, "data1", "a" ) == 0 &&  
       fopen_s( &stream2, "data2", "w" ) == 0 )  
   {  
      if( setvbuf( stream1, buf, _IOFBF, sizeof( buf ) ) != 0 )  
         printf( "Incorrect type or size of buffer for stream1\n" );  
      else  
         printf( "'stream1' now has a buffer of 1024 bytes\n" );  
      if( setvbuf( stream2, NULL, _IONBF, 0 ) != 0 )  
         printf( "Incorrect type or size of buffer for stream2\n" );  
      else  
         printf( "'stream2' now has no buffer\n" );  
      _fcloseall();  
   }  
}  
```  
  
```Output  
'stream1' now has a buffer of 1024 bytes  
'stream2' now has no buffer  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [setbuf](../../c-runtime-library/reference/setbuf.md)