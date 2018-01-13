---
title: _flushall | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _flushall
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
f1_keywords: _flushall
dev_langs: C++
helpviewer_keywords:
- flushall function
- flushing streams
- streams, flushing
- _flushall function
ms.assetid: 2cd73562-6d00-4ca2-b13c-80d0ae7870b5
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 76a99cbdd3376579bac0126704a4df496905446e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: tr-TR
ms.lasthandoff: 12/21/2017
---
# <a name="flushall"></a>_flushall
Tüm akışlar aktarır; Tüm arabellekler temizler.  
  
## <a name="syntax"></a>Sözdizimi  
  
```  
int _flushall( void );  
```  
  
## <a name="return-value"></a>Dönüş Değeri  
 `_flushall`Açık akış (girdi ve çıktı) sayısını döndürür. Döndürülen hata yoktur.  
  
## <a name="remarks"></a>Açıklamalar  
 Varsayılan olarak, `_flushall` için yazar uygun dosyaları açık çıkış akışları ile ilişkili tüm arabelleklerinin içeriğini işlevi. Açık giriş akışları ile ilişkili tüm arabellekler kendi geçerli içeriğini temizlenir. (Bu arabellekleri normalde verileri otomatik olarak diske yazmak için en iyi zamanı belirler işletim sistemi tarafından korunur: bir arabellek dolduğunda, bir akış kapalıyken veya ne zaman bir program akışları kapatmadan sona erer.)  
  
 Okuma yapılan bir çağrı izliyorsa `_flushall`, yeni verileri arabellekleri giriş dosyalarından okuyun. Çağrısından sonra tüm akışlar açık kalmaya `_flushall`.  
  
 Çalışma Zamanı Kitaplığı commit-to-disk özellik kritik verileri doğrudan diske yerine işletim sistemi arabellekleri için yazılmış emin olun olanak sağlar. Varolan bir programı'nı yeniden yazma işlemi olmadan, programın nesne dosyaları Commode.obj ile bağlayarak bu özelliği etkinleştirebilirsiniz. Sonuçta elde edilen yürütülebilir dosyada çağrılar `_flushall` tüm arabelleklerinin içeriğini diske yazma. Yalnızca `_flushall` ve `fflush` Commode.obj tarafından etkilenir.  
  
 Commit-to-disk özelliği denetleme hakkında daha fazla bilgi için bkz: [akış g/ç](../../c-runtime-library/stream-i-o.md), [fopen](../../c-runtime-library/reference/fopen-wfopen.md), ve [_fdopen](../../c-runtime-library/reference/fdopen-wfdopen.md).  
  
## <a name="requirements"></a>Gereksinimler  
  
|İşlev|Gerekli başlık|  
|--------------|---------------------|  
|`_flushall`|\<stdio.h >|  
  
 Daha fazla uyumluluk bilgileri için bkz: [Uyumluluk](../../c-runtime-library/compatibility.md) giriş.  
  
## <a name="example"></a>Örnek  
  
```  
// crt_flushall.c  
// This program uses _flushall  
// to flush all open buffers.  
  
#include <stdio.h>  
  
int main( void )  
{  
   int numflushed;  
  
   numflushed = _flushall();  
   printf( "There were %d streams flushed\n", numflushed );  
}  
```  
  
```Output  
There were 3 streams flushed  
```  
  
## <a name="see-also"></a>Ayrıca Bkz.  
 [Akış g/ç](../../c-runtime-library/stream-i-o.md)   
 [_commit](../../c-runtime-library/reference/commit.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [fflush](../../c-runtime-library/reference/fflush.md)   
 [setvbuf](../../c-runtime-library/reference/setvbuf.md)