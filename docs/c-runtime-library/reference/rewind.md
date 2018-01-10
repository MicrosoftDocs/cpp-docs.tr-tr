---
title: Geri Sar | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: rewind
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
f1_keywords: rewind
dev_langs: C++
helpviewer_keywords:
- rewind function
- repositioning file pointers
- file pointers [C++], repositioning
- file pointers [C++]
ms.assetid: 1a460ce1-28d8-4b5e-83a6-633dca29c28a
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 78cb2d761e7625dac7073927b7b7f1a06fcf1759
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="rewind"></a>geri sar
Dosya işaretçisini dosya başına yeniden konumlandırır.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
  
      void rewind(  
   FILE *stream   
);  
```  
  
#### <a name="parameters"></a>Parametreler  
 `stream`  
 İşaretçi **dosya** yapısı.  
  
## <a name="remarks"></a>Açıklamalar  
 **Geri sarma** işlevi ile ilişkili dosya işaretçisini yeniden konumlandırır `stream` dosya başına. Çağrı **geri sarma** benzer  
  
 **(void) fseek (** `stream` **, 0L** `SEEK_SET` **);**  
  
 Ancak, farklı `fseek`, **geri sarma** akış için hata göstergeleri yanı sıra dosya sonu göstergesi temizler. Ayrıca, farklı `fseek`, **geri sarma** işaretçinin başarıyla taşındı olup olmadığını belirten bir değer döndürmüyor.  
  
 Klavye arabellek silmek için kullanın **geri sarma** akış ile `stdin`, klavye ile varsayılan olarak ilişkili olduğu.  
  
 Akış ise bir `NULL` işaretçi, geçersiz parametre işleyicisi çağrılır, açıklandığı gibi [parametre doğrulaması](../../c-runtime-library/parameter-validation.md). Bu işlev, yürütme devam etmek için izin verilip verilmediğini, döndürür ve `errno` ayarlanır `EINVAL`.  
  
 Bunlar ve diğer hata kodları hakkında daha fazla bilgi için bkz: [_doserrno, errno, _sys_errlist ve _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|Yordam|Gerekli başlık|  
|-------------|---------------------|  
|**rewind**|\<stdio.h >|  
  
 Ek uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="libraries"></a>Kitaplıklar  
 Tüm sürümleri [C çalışma zamanı kitaplıkları](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Örnek  
  
```  
// crt_rewind.c  
/* This program first opens a file named  
 * crt_rewind.out for input and output and writes two  
 * integers to the file. Next, it uses rewind to  
 * reposition the file pointer to the beginning of  
 * the file and reads the data back in.  
 */  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int data1, data2;  
  
   data1 = 1;  
   data2 = -37;  
  
   fopen_s( &stream, "crt_rewind.out", "w+" );  
   if( stream != NULL )  
   {  
      fprintf( stream, "%d %d", data1, data2 );  
      printf( "The values written are: %d and %d\n", data1, data2 );  
      rewind( stream );  
      fscanf_s( stream, "%d %d", &data1, &data2 );  
      printf( "The values read are: %d and %d\n", data1, data2 );  
      fclose( stream );  
   }  
}  
```  
  
## <a name="output"></a>Çıkış  
  
```  
The values written are: 1 and -37  
The values read are: 1 and -37  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)